        private void ActorUpdate(List<Actor> actors)
        {
            for (int i = 0; i < actors.Count; ++i)
            {
                if (actors[i].State != ActorState.Dead)
                    actors[i].ActorUpdate();
                elseㄴ
                {
                    actors.RemoveAt(i);
                    --i;
                }
            }
        }


        actor가 사망하여 리스트에서 삭제되는 과정 이후 반복문으로 돌아갈 때,
        ++i; 로 인해 인덱스가 스킵될 수 있으므로 삭제 과정 이후 --i;를 추가함.