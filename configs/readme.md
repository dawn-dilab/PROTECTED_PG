# 实验结果记录

## 机器六

### cartpole
1. eps=0.15  "mode": "adv_ppo", 无归一化 gym==0.25.1 torch==1.13.1+cu116 iter=10 step =2441 因为 是离散的, 所以没有跑完iter.
/root/code/PROTECTED_PG/protected_cartpole/agents/5dc1e64f-4013-4e78-874f-352a6e9ef933

2. eps=0.15  "mode": "adv_ppo", 无归一化 gym==0.25.1 torch==1.13.1+cu116 iter=6 step =1200 
/root/code/PROTECTED_PG/protected_cartpole/agents/0f04c5da-8d1e-4f41-8960-9b1da06d2ddb
```shell
--config-path
configs/config_cartpole.json
--deterministic
--ref-model-list
/root/code/PROTECTED_PG/protected_cartpole/agents/0f04c5da-8d1e-4f41-8960-9b1da06d2ddb/model_0
/root/code/PROTECTED_PG/protected_cartpole/agents/0f04c5da-8d1e-4f41-8960-9b1da06d2ddb/model_1
/root/code/PROTECTED_PG/protected_cartpole/agents/0f04c5da-8d1e-4f41-8960-9b1da06d2ddb/model_2
--results-log
logs/test_cartpole_random.log
--attack-eps 0.15
--attack-method
random

```
random  eps==0.15
mean: 432.22, std:155.6621071423614, min:28.0, max:500.0
mean: 500.0, std:0.0, min:500.0, max:500.0
mean: 210.9, std:14.793579688500008, min:182.0, max:246.0

mean: 500.0, std:0.0, min:500.0, max:500.0
mean: 500.0, std:0.0, min:500.0, max:500.0
mean: 222.54, std:9.215660584027605, min:205.0, max:240.0

mean: 435.47, std:162.6621071423614, min:36.0, max:500.0
```shell
--config-path
configs/config_cartpole.json
--deterministic
--ref-model-list
/root/code/PROTECTED_PG/protected_cartpole/agents/0f04c5da-8d1e-4f41-8960-9b1da06d2ddb/model_0
/root/code/PROTECTED_PG/protected_cartpole/agents/0f04c5da-8d1e-4f41-8960-9b1da06d2ddb/model_1
/root/code/PROTECTED_PG/protected_cartpole/agents/0f04c5da-8d1e-4f41-8960-9b1da06d2ddb/model_2
--results-log
logs/test_cartpole_advpolicy.log
--attack-eps 0.15
--attack-method
advpolicy
--attack-advpolicy-network 
/root/code/PROTECTED_PG/protected_cartpole/agents/0f04c5da-8d1e-4f41-8960-9b1da06d2ddb/model_0
```
mean: 500.0, std:0.0, min:500.0, max:500.0
mean: 129.5, std:7.849203781276162, min:118.0, max:150.0
mean: 125.48, std:4.045936232814354, min:118.0, max:135.0


### pendulum
1. eps=0.15 "mode": "adv_pa_ppo", 无归一化 gym==0.25.1 torch==1.13.1+cu116 iter=10 step =2441 使用config_pendulum_0.json 但是优化不了.
融合了 PROTECTED 的config_hopper配置.  iter=10 step =2441 
/root/code/PROTECTED_PG/protected_pendulum/agents/4255b453-bc06-4ec0-bf79-8447f4177153


2. 恢复atla的配置. 只是 "mode": "adv_pa_ppo" 其他配置 无归一化 gym==0.25.1 torch==1.13.1+cu116 iter=6 step =1200 
/root/code/PROTECTED_PG/protected_pendulum/agents/3bdae3dd-a95e-4e98-909a-b43d4627c7ab

3. 恢复atla的配置. 只是 "mode": "adv_ppo" 其他配置 无归一化 gym==0.25.1 torch==1.13.1+cu116 iter=3 step =1600 
/root/code/PROTECTED_PG/protected_pendulum/agents/870d88ec-29f3-41ce-8e90-37262af32cd4

random eps==0.15
mean: -150.4355530669394, std:95.55907921174585, min:-366.39597968177765, max:-2.940439150159504
最坏攻击 eps==0.15
mean: -134.89411917567915, std:85.8674128049545, min:-337.11799904828626, max:-0.20085118409637254
nature
mean: -141.60836097692348, std:89.2439893080641, min:-349.394725791293, max:-4.919311146201587





### 13Bus
```shell
--config-path
/root/code/PROTECTED_PG/configs/config_13Bus.json
--deterministic
--ref-model-list
/root/code/PROTECTED_PG/protected_13Bus/agents/b4c960af-98f7-4e97-bfc4-b5d84739e79a/model_0
/root/code/PROTECTED_PG/protected_13Bus/agents/b4c960af-98f7-4e97-bfc4-b5d84739e79a/model_1
/root/code/PROTECTED_PG/protected_13Bus/agents/b4c960af-98f7-4e97-bfc4-b5d84739e79a/model_2
--results-log
logs/test_13Bus_adv.log
--attack-eps
0.15
--attack-method
advpolicy
--attack-advpolicy-network
/root/code/PROTECTED_PG/protected_13Bus/agents/b4c960af-98f7-4e97-bfc4-b5d84739e79a/model_0
```

1. 恢复atla的配置. 只是 "mode": "adv_ppo" 其他配置 无归一化 gym==0.18.0  iter=3 step =400 torch==2.0.0+cu118 eps=0.15训练
/root/code/PROTECTED_PG/protected_13Bus/agents/b4c960af-98f7-4e97-bfc4-b5d84739e79a
random eps=0.15
mean: -6.16786906443219, std:0.08068322912612914, min:-6.362495073917917, max:-6.0030425078891545
natural
mean: -5.953492161127232, std:8.881784197001252e-16, min:-5.953492161127231, max:-5.953492161127231
worst eps=0.15
mean: -6.010083156913338, std:8.881784197001252e-16, min:-6.010083156913339, max:-6.010083156913339

2. 恢复atla的配置. 只是 "mode": "adv_ppo" 其他配置 无归一化 gym==0.18.0  iter=3 step =400 torch==2.0.0+cu118 eps=0.3 训练
Models saved to /root/code/PROTECTED_PG/protected_13Bus/agents/4f682d55-a24f-496b-b551-c8e0a5cd5f64


### 34Bus
```shell
--config-path
/root/code/PROTECTED_PG/configs/config_34Bus.json
--deterministic
--ref-model-list
/root/code/PROTECTED_PG/protected_34Bus/agents/a25cbb9c-1388-4b2d-b58d-29ddfdf711dd/model_0
/root/code/PROTECTED_PG/protected_34Bus/agents/a25cbb9c-1388-4b2d-b58d-29ddfdf711dd/model_1
/root/code/PROTECTED_PG/protected_34Bus/agents/a25cbb9c-1388-4b2d-b58d-29ddfdf711dd/model_2
--results-log
logs/test_34Bus_adv.log
--attack-eps
0.15
--attack-method
advpolicy
--attack-advpolicy-network
/root/code/PROTECTED_PG/protected_34Bus/agents/a25cbb9c-1388-4b2d-b58d-29ddfdf711dd/model_0
```

1. 恢复atla的配置. 只是 "mode": "adv_ppo" 其他配置 无归一化 gym==0.18.0  iter=3 step =150 torch==2.0.0+cu118 eps=0.15训练
/root/code/PROTECTED_PG/protected_34Bus/agents/a25cbb9c-1388-4b2d-b58d-29ddfdf711dd
PROTECTED
nature
mean: -11.487487056097716, std:0.03860743372041382, min:-11.577846179583956, max:-11.439227549322826 
mean: -10.37529047428378, std:0.07474979278517405, min:-10.476927575505613, max:-10.21561159255108
mean: -9.758083878157173, std:0.07833510209906717, min:-9.88239739927799, max:-9.636620380042391

random eps=0.15
mean: -12.793244249976688, std:0.32540056400074024, min:-13.430145846092598, max:-12.168230589013207
mean: -10.718827674773753, std:0.29670631886006343, min:-11.547633234604533, max:-10.067217787713869
mean: -10.144870991446755, std:0.2248494223087684, min:-10.905934192975364, max:-9.819057313570058

worst eps=0.15
mean: -11.581423504790871, std:0.03562291892658584, min:-11.660240127092809, max:-11.531048184394535
mean: -10.309581998823976, std:0.10270480435361565, min:-10.453228363446698, max:-10.120540452322246
mean: -9.74876375386065, std:0.1913881687562583, min:-10.026558353702058, max:-9.468779150989713

### 123Bus
1. 恢复atla的配置. 只是 "mode": "adv_ppo" 其他配置 无归一化 gym==0.18.0  iter=3 step =85 torch==2.0.0+cu118 eps=0.15训练 
reset idx变化 通常会变好
/root/code/PROTECTED_PG/protected_123Bus/agents/2b25520c-1546-4a4f-ad88-1ab9a8fc8c30

nature
mean: -10.337811108872335, std:0.02267483204757285, min:-10.395957489510595, max:-10.295168534719592
mean: -12.386683066647219, std:0.028566646553152955, min:-12.493390720893355, max:-12.341530704856332
mean: -13.523461791894874, std:0.022939097780975592, min:-13.581295444851968, max:-13.481964645973893

random eps=0.15
mean: -10.836249435526163, std:0.1643382406206697, min:-11.110043391348489, max:-10.435072443358537
mean: -12.852636782915237, std:0.14481807902166405, min:-13.295335176788702, max:-12.544043213018185
mean: -13.728692077531784, std:0.09170764726248493, min:-13.943487283458536, max:-13.549656040045372

worst eps=0.15
mean: -10.361848262122539, std:0.022839852137409897, min:-10.420384871466156, max:-10.318786104808957
mean: -12.370239563525923, std:0.019529610173930255, min:-12.402112299546571, max:-12.328422122329354
mean: -13.503339973844133, std:0.023373735420000503, min:-13.562919592061094, max:-13.460956233085422

2. 恢复atla的配置. 只是 "mode": "adv_ppo" 其他配置 无归一化 gym==0.18.0  iter=3 step =85 torch==2.0.0+cu118 eps=0.15训练 
reset idx=1
/root/code/PROTECTED_PG/protected_123Bus/agents/6bef0d15-b04b-4602-b06b-f71ea151b863

nature
mean: -10.32065162744691, std:0.032257795356775636, min:-10.44729188966453, max:-10.274998514972705
mean: -13.879341035241008, std:0.018006496173088127, min:-13.904356492637838, max:-13.840892913475273 
mean: -13.168078685225703, std:0.02460128439734868, min:-13.24257784820862, max:-13.127023487059798

random eps=0.15
mean: -10.949882178170236, std:0.13573956227014305, min:-11.207509822889179, max:-10.661362248664066
mean: -14.11191457427882, std:0.10993478541205551, min:-14.336521364946677, max:-13.896885836750284
mean: -13.4334978862424, std:0.1140365368343779, min:-13.744833623747258, max:-13.172075334094263

worst eps=0.15
mean: -10.44074950805276, std:0.022508700515875196, min:-10.49753448253988, max:-10.398014576836163
mean: -13.857697814065569, std:0.01799146988089888, min:-13.882567677179026, max:-13.819272654365998
mean: -13.149316360690797, std:0.024530614871368255, min:-13.22348650808978, max:-13.108323209393376