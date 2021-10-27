# CKAD Note Section 5 Observability


## 70. Readiness and Liveness Probes

<br>

### Readiness Probes


透過前面的章節我們可以得知 `Pod` 具有狀態 (status) 與 條件 (condition)，前者顯示 lifecycle 階段 (pending, containerCreating, running)


- pending: scheduler 正在安排 `pod` 到 worker-node 上，或者有問題 (`kubectl describe` 可以查)
- containerCreating: `pod` 已經被放在 worker-node 上，正在建立容器
- running: 執行中


Condition 的部分就有點類似細項，透過 `kubectl describe` 可以觀察。

<br>

![pod_condition_0](pod_condition_0.jpg)

▲ `pod` condition 項目列表

<br>

不過在這麼多項目當中，在這個章節我們只關心 **<span style='color:blue'>ContainersReady 與 Ready</span>**


**<span style='color:red'>`kubectl get pods` 只能看到 status， `kubectl describe pod` 才能看到 condition。</span>**