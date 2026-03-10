# docs

*Tamdiu discendum est, quoad vivas, quemadmodum vivas*.
-Seneca

```mermaid
graph TB
  subgraph "Control Plane"
    API[kube-apiserver]
    ETCD[(etcd)]
    SCH[kube-scheduler]
    CM[kube-controller-manager]
    
    API --- ETCD
    API --- SCH
    API --- CM
  end

  subgraph "Node 1 (Worker)"
    K1[kubelet]
    P1[kube-proxy]
    D1[Container Runtime]
    
    K1 --- D1
  end

  subgraph "Node 2 (Worker)"
    K2[kubelet]
    P2[kube-proxy]
    D2[Container Runtime]
    
    K2 --- D2
  end

  API === K1
  API === K2
    end
