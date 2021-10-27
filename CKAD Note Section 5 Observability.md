# CKAD Note Section 5 Observability


## 70. Readiness and Liveness Probes

<br>

### Readiness Probes


透過前面的章節我們可以得知 `Pod` 具有狀態 (status) 與 條件 (condition)，前者顯示 lifecycle 階段 (pending, containerCreating, running)


- pending: scheduler 正在安排 `pod` 到 worker-node 上，或者有問題 (`kubectl describe` 可以查)
- containerCreating: `pod` 已經被放在 worker-node 上，正在建立容器
- running: 執行中


**<span style='color:red'>`kubectl get pods` 只能看到 status， `kubectl describe pod` 才能看到 condition。</span>**