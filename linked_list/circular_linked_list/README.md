# Circular Linked List

[뒤로 가기](..)

## exercise 00
- 아래와 같은 list.h를 사용 합니다.
	```
	typedef struct	s_node
	{
		void		*data;
		struct s_node	*prev;
		struct s_node	*next;
	}		t_node;

	typedef struct s_linked_list
	{
		unsigned int	size;
		t_node		**head;
	}
	```

### list_init
- t_linked_list형 struct를 반환 하는 함수를 작성하세요.
- 반환되는 t_linked_list는 메모리 할당과 초기화를 거쳐야합니다.
	```
	t_linked_list *list_init(void);
	```

### create_elem
- t_node형 새로운 요소를 생성하는 함수를 작성하세요.
	```
	t_node *create_elem(void *data);
	```
	
### list_add
- 목록의 n번 인덱스에 data를 갖는 새로운 요소를 생성하는 함수를 작성하세요.
- n이 목록의 요소의 수보다 클 경우엔 마지막 위치에 생성하세요.
- 생성된 요소의 인덱스를 반환 합니다.
	```
	int list_add(t_linked_list *list, void *data, int n);
	```

### list_size
- 목록에 있는 요소의 개수를 반환하는 함수를 작성하세요.
	```
	int list_size(t_linked_list *list);
	```

### list_get
- 목록에서 n번 인덱스의 요소를 반환하는 함수를 작성하세요.
	```
	t_node *list_get(t_linked_list *list, int n);
	```

### list_find
- 목록에서 data의 값이 같은 요소를 반환하는 함수를 작성하세요.
- 없을 경우엔 널포인터를 반환 합니다.
	```
	t_node *list_find(t_linked_list *list, int data);
	```

### list_remove
- 목록에서 n번 인덱스의 요소를 삭제하는 함수를 작성하세요.
- 요소의 데이터는 free_data를 사용해서 메모리 할당을 해제해야 합니다.
	```
	void list_remove(t_linked_list *list, int n, void (*free_data)(void *));
	```

### list_clear
- 목록 전체를 삭제하는 함수를 작성하세요.
- 요소의 데이터는 free_data를 사용해서 메모리 할당을 해제해야 합니다.
	```
	void list_clear(t_linked_list *list, void (*free_data)(void *));
	```

### list_foreach
- 목록에 있는 모든 요소의 data에 매개변수로 주어진 함수 f를 적용하는 함수를 작성하세요.
	```
	void list_foreach(t_linked_list *list, void (*f)(void *));
	```

[뒤로 가기](..)