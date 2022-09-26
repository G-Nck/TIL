# 방사형 차트
###2022-09-26

["How to make RPG Radar Chart (Unity Tutorial) - Code Monkey"](https://youtu.be/twjMW7CxIKk) 유튜브 자료를 참고했다.
위 자료에서 나온 코드는 오직 오각형만 사용할 수 있는 코드였기에,
다각형을 생성하는 알고리즘을 구현해 적용했다.


```cs
  private void UpdateVisual(int angle, float[] normalizedValues)
    {
        Vector3[] vertices = new Vector3[angle + 1];
        Vector2[] uv = new Vector2[angle + 1];
        int[] triangles = new int[angle * 3];

        vertices[0] = Vector3.zero;
        triangles[0] = 0;

        for(int i = 0; i < angle; i++)
        {
            vertices[i + 1] = Quaternion.Euler(0, 0, -(360f / angle) * i) * Vector3.up * chartSize * normalizedValues[i];

         //피자 조각처럼 삼각형을 만듬.
		 //한바퀴를 돌면 다시 index 1번째 정점을 향해야 하기 때문에.
		 //(i + 1) % (angle) + 1 값을 사용. 
		 //((i + 2) % (angle) 의 경우 값이 0이 나오는 케이스가 생겨서 안됨.)
            triangles[i * 3] = 0;
            triangles[i * 3 + 1] = i + 1;
            triangles[i * 3 + 2] = (i + 1) % (angle) + 1;
        }

        Mesh mesh = new Mesh();
        mesh.vertices = vertices;
        mesh.uv = uv;
        mesh.triangles = triangles;

        canvasRenderer.SetMesh(mesh);
        canvasRenderer.SetMaterial(chartMaterial, null);
    }
```
