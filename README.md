# IPC-2023


1. MDPS VS POMDPS
- MDPS: fully observable, assume that the state of the system is fully observable i.e. the agent has complete knowledge of the current state of the system and can use this information to make decisions. e.g. Chess.
- POMDPS: partially observable environment, the agent only has access to partial observations of the state, and must maintain a belief state to reason about the true state of the system. e.g. Super Mario game

2. MDPS might not be valid in real world problems where the past history may be relevant to the future state - POMDPS and RNN, etc are used in that case.  



### Trained for 100k epochs, Optimizer = Rmsprop
FOR LEARNING RATE = 0.01, train_return=-0.000180 test_return=-0.000187

FOR LEARNING RATE = 0.001, train_return=-0.000029 test_return=-0.000036

FOR LEARNING RATE = 0.0001, train_return=0.000003 test_return=-0.000004

FOR LEARNING RATE = 0.0003, train_return=-0.000004 test_return=-0.000011


### Trained for 1000 epochs, Optimizer = RMSprop
FOR LEARNING RATE = 0.01, train_return=-0.000052 test_return=-0.000059

FOR LEARNING RATE = 0.001, train_return=-0.000030 test_return=-0.000037

FOR LEARNING RATE = 0.0001, train_return=0.000003 test_return=-0.000004

FOR LEARNING RATE = 0.0003, train_return=-0.000004 test_return=-0.000011



### Trained for 1000 epochs, Optimizer = adam

FOR LEARNING RATE = 0.01, train_return=-0.000039 test_return=-0.000045

FOR LEARNING RATE = 0.001, train_return=-0.000030 test_return=-0.000037

FOR LEARNING RATE = 0.0001, train_return=0.000002 test_return=-0.000005

FOR LEARNING RATE = 0.0003, train_return=0.000006 test_return=-0.000001


### Trained for 1000 epochs, Optimizer = adagrad

FOR LEARNING RATE = 0.01, train_return=0.000000 test_return=-0.000006

FOR LEARNING RATE = 0.001, train_return=0.000006 test_return=-0.000001

FOR LEARNING RATE = 0.0001, train_return=-0.000359 test_return=-0.000366

FOR LEARNING RATE = 0.0003, train_return=-0.000195 test_return=-0.000201




# ------------------------------------------- SAY HELLO TO JaxDeepReactivePolicy(topology = [256, 128]) ----------------------------------------------

### Trained for 1000 epochs, Optimizer = rmsprop, JaxDeepReactivePolicy

FOR LEARNING RATE = 0.01, train_return=-0.000024 test_return=-0.000031

FOR LEARNING RATE = 0.001, train_return=-0.002088 test_return=-0.001904

FOR LEARNING RATE = 0.0001, train_return=-0.001759 test_return=-0.001705

FOR LEARNING RATE = 0.0003, train_return=-0.003328 test_return=-0.003029

















Note: planner.optimize() returns a generator that yields a dictionary callback at the end of each training epoch. The dictionary contains various performance metrics, such as train_return and test_return, as well as the current model parameters, which are stored under the key params. So, if you want to access the final model parameters after training, you can simply use callback['params'].


policy_weights is a dictionary with keys representing the names of the actions in the policy, and values representing the weight to be assigned to each of those actions.

In the context of reinforcement learning or decision-making problems, the weights in a policy are typically used to balance exploration and exploitation. A higher weight indicates that the corresponding action should be chosen more often, which can lead to more exploration of the state space. Conversely, a lower weight indicates that the corresponding action should be chosen less often, which can lead to more exploitation of the current knowledge about the state space.

In the example you provided, the actions are 'cut-out' and 'put-out', and they are assigned equal weights of 10.0 each. This means that the planner will attempt to balance exploration and exploitation by choosing these two actions roughly equally often.


It seems that the variable "subs" is of type "NoneType" and therefore has no attribute "items". The code is trying to iterate over the items of the "subs" dictionary, but since it is None, it is causing the error.
