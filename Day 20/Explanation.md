"Explanation here..." 
Explanation:
Node Class:
This is a nested class representing a doubly linked list node.
Each node contains an integer key, an integer value, and pointers to the previous and next nodes in the linked list.
LRUCache Class:
This is the main LRU Cache class.
It has a fixed capacity (cap) that is specified during its instantiation.
It uses an unordered_map<int, Node*> named m to store key-value pairs, where the key is the integer key, and the value is a pointer to the corresponding Node.
head and tail Nodes:
The LRUCache class has two dummy nodes: head and tail.
These nodes act as sentinels in the doubly linked list, helping to simplify the edge cases and avoid dealing with null pointers.
head is the first node in the linked list, and tail is the last node.
addNode Function:
This function is used to add a new node to the front of the doubly linked list (right after head).
It takes a Node* newnode as input, representing the node to be added.
The function updates the pointers of the new node, the previous first node, and head to include the new node as the new first node.
deleteNode Function:
This function is used to delete a node from the doubly linked list.
It takes a Node* delnode as input, representing the node to be deleted.
The function updates the pointers of the previous and next nodes to exclude the node to be deleted, effectively removing it from the linked list.
get Function:
This function is used to retrieve a value from the cache based on the given key.
If the key exists in the cache (m.find(key) != m.end()), it retrieves the corresponding node (resNode), extracts its value (ans), and performs the following steps:
Erase the key-value pair from the m unordered map.
Delete the node from its current position in the linked list using deleteNode.
Add the node to the front of the linked list using addNode, making it the most recently used node.
Update the m map to store the key with the most recently used node.
If the key doesn't exist in the cache, it returns -1.
put Function:
This function is used to insert or update a key-value pair in the cache.
If the key already exists in the cache, it updates the value by performing the following steps:
Erase the existing key-value pair from the m unordered map.
Delete the corresponding node from its current position in the linked list using deleteNode.
If the cache is full (i.e., m.size() == cap), it removes the least recently used node from the cache by erasing the key-value pair from the m map and deleting the node from the end of the linked list using deleteNode.
After handling the eviction (if needed), it creates a new node using new Node(key, value) and adds it to the front of the linked list using addNode.
Finally, it updates the m map to store the key with the newly added node.