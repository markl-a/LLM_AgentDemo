graph TD
    A[用户提供的自定义 Docker 镜像] -- B[OpenHands 后端]
    B --构建 C[OH 运行时镜像]
    C --启动 D[Action 执行器]
    D --初始化 E[浏览器]
    D --初始化 F[Bash Shell]
    D --初始化 G[插件]
    G --初始化 L[Jupyter 服务器]

    B --生成 H[代理]
    B --生成 I[EventStream]
    I ---通过 REST API
    执行 Action 获取 Observation
     D

    H --生成 Action I
    I --获取 Observation H

    subgraph Docker 容器
    D
    E
    F
    G
    L
    end