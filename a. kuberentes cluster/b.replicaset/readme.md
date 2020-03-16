## Pod and ReplicaSet
RS is a term for API objects in Kubernetes that refer to Pod replicas. bisa di bilang untuk control dari set sebuah pod. 
RS memastikan bahwa Pod, berjalan secara baik setiap saat dan dapat spesifik jumlahnya berdasarkan user.

Untuk lebih jelasnya di bawah


a. kube-controller-manager daemon helps to maintain the resource running in its desired state. example. have 3 pod replica
b. kube-scheduler daemon on master, takes charge of assigning tasks to healthy noes
c. The selector is used for deciding which pods it covers.

