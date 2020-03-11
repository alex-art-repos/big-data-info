Cluster management, consensus
=============================

1.RAFT
- http://thesecretlivesofdata.com/raft/

consul
- strong consistency и для всех апдейтов используют RAFT, т.е. пишет на диск и ждет подтверждения от всех реплик, что они закоммитили
- требования по количеству инстансов, рекомендуют 3-5
- сервер + агенты, агенты используют gossip друг к другу, gossip на агентах полностью не отключить, он необходим для нормальной работы.
- для снижения нагрузки на лидера можно использовать stale режим для чтения, чтобы не лидеры отвечали тем, что есть.
- чувствителен к всплескам IO (запись), загрузке CPU (чтение) - начинаются рандомные потери лидера и перевыборы.
- хорошие доки, есть встроенный UI и API
- написан на go

etcd
- Похож на consul.
- RAFT
- требования по количеству инстансов, рекомендуют 3-5
- без агентов
- доки на github, есть API и сторонний UI
- написан на go

zookeeper
- видимо, свой протокол (не нашел упоминаний RAFT), но тоже с подтвержденим от followers и лидерством
- заявлен in-mem, но все равно пишет на диск для recovery
- требования по количеству инстансов
- много информации, популярный
- написан на java

идеальный вариант
- честный in-mem
- multimaster или асинхронная репликация, без явного лидера, принимающего все запросы
- встроенный и\или удобно разворачиваемый, без жестких требований к количеству узлов и т.д.
- без агентов
- лишний трафик (gossip, пинги, heartbeat и проч) может быть только между серверами, лимитирован от клиентов(если есть).
- актуальный, с нормальным API
