# POLICY EVALUATION

## AIM
To develop a Python program to evaluate the given policy.

## PROBLEM STATEMENT
To find best policy from two policies which are defined by user using policy evaluation function. Where the mdp includes 16 states from 0-15, 0 is the starting state, assigning some 4 random state as holes and 15 is the goal state and then we need to calculate optimal state value function for each state such that we can reach goal using optimal policy using policy evaluation.

## POLICY EVALUATION FUNCTION
def policy_evaluation(pi, P, gamma=1.0, theta=1e-10):
    prev_V = np.zeros(len(P), dtype=np.float64)
    # Write your code here to evaluate the given policy
    while True:
      V = np.zeros(len(P))
      for s in range(len(P)):
        for prob, next_state, reward, done in P[s][pi(s)]:
          V[s] += prob * (reward + gamma *  prev_V[next_state] * (not done))
      if np.max(np.abs(prev_V - V)) < theta:
        break
      prev_V = V.copy()
    return V

## OUTPUT:
Policies:
<img width="1868" height="631" alt="424312161-16a36653-f9b9-48b9-97c8-61a569db52a6" src="https://github.com/user-attachments/assets/b26ace8a-ce5a-4fce-876f-46285d01cf36" />
<img width="1532" height="712" alt="424312388-6dc36748-bdb6-4614-81f4-51ebc4a8eb2b" src="https://github.com/user-attachments/assets/c4456fb3-cd7a-4836-b9a0-b7856739b920" />
state value function:
<img width="1837" height="426" alt="424312855-170aabea-c21c-4ad8-8d7a-b839f187c7a2" src="https://github.com/user-attachments/assets/e7cfbe30-6c53-4c7a-8db8-5c3260c37d04" />
Best policy:
<img width="1807" height="276" alt="424313202-47b0b0bb-56ee-41bf-8621-81d946fdf70d" src="https://github.com/user-attachments/assets/a424e73c-b546-49ec-9208-3cbee8b55958" />

## RESULT:
Thus, The Python program to evaluate the given policy is successfully executed.

