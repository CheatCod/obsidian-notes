```plantuml
!theme materia-outline
skinparam classAttributeIconSize 0
abstract class Node {
	string content
	shared_ptr<Node> left;
	shared_ptr<Node> right;
	
	{abstract} accept(NodeVisitor);
	{abstract} shared_ptr<Node> getLeft();
	{abstract} shared_ptr<Node> getRight();
}

class NumNode {
	accept(NodeVisitor)
}

class PlusNode {
	accept(NodeVisitor)
}

class MinusNode {
	accept(NodeVisitor)
}

class MultNode {
	accept(NodeVisitor)
}

class DivideNode {
	accept(NodeVisitor)
}

abstract class NodeVisitor {
	{abstract} string visit(MultNode);
	{abstract} string visit(PlusNode);
	{abstract} string visit(MinusNode);
	{abstract} string visit(DivideNode);
}

class EvalVisitor{
int result;
 string visit(MultNode);
 string visit(PlusNode);
 string visit(MinusNode);
 string visit(DivideNode);
}

NodeVisitor <|-- EvalVisitor

Node <|-- NumNode
Node <|-- PlusNode
Node <|-- MinusNode
Node <|-- MultNode
Node <|-- DivideNode
```

$\set{A \land C, B}$

$\set{A \land D, B}$