유니티 오브젝트에 NavMeshAgent 컴포넌트를 추가 이후, 
Rigidbody와 Collider를 추가할 때
Rigidbody의 isKinemetic 옵션을 체크하지 않으면 NavMeshAgent가
NavMesh를 제대로 인식하지 못하는 버그가 생길 수 있다.