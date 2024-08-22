> Each instruction in a [[DockerFile]] `roughly` translates to an **image layer**.

![[Pasted image 20240821213506.png]]
## caching layers
- if a layer is unchanged, it gets from the build cache
- if a layer is changed from previous build, all others that follow becomes built again
![[Pasted image 20240821213550.png]]