# ContraintModelEngine
Pet project used to discover what it looks like to model, and leverage a finite constrained field


# Shower thought
This may look like writing an entirely new modeling format "think XML/XMI" but with native support for relational concerns and the capability to capture comparison and linking?
Maybe it has native query semantics like FACE?
Definitely native comparison, and constraint features

example of XML to new thing ( relational model markup language )
<tag name="example", id="GUID">
  <valueType name="child1", id="GUID"/>
  <valueType name="child2", id="GUID"/>
</tag>

This XML would look like:

tag (name: "example", id="GUID")
{
  value(name: "powerLevel" id="GUID", type=enum)
  {
    Eco,
    Normal,
    Sport
  }
  value(name: "Speed" id="GUID", type=int);
  
  value(name: "isActive" id="GUID", type=bool);
}


constrain example.speed with enum example.powerLevel
{
  on Eco: constraint<int>(min: 0, max: 4)
  on Normal: constraint<int>(min: 0, max: 7)
  on Sport: constraint<int>(min: 0, max: 10)
}



