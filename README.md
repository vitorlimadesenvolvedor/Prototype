Prototype

```

public int Age;
public DateTime BirthDate;
public string Name;
public IdInfo IdInfo;
        
        
public Person ShallowCopy()
{
  // Faz a cópia das propriedades com tipos primitvos. Também faz a cópia das propriedades de tipos complexos,
  // porém, se o objeto de origem do clone sofrer alguma mudança nesta propriedade de tipo complexo,
  // a valor desta propriedade no objeto clone também sofrerá alteração
  return (Person)MemberwiseClone();
}

public Person DeepCopy()
{
  // Neste caso está sendo criado um novo objeto para a propriedade de tipo complexo, tornando-o independente do objeto de origem
  Person clone = (Person)MemberwiseClone();
  clone.IdInfo = new IdInfo(IdInfo.IdNumber);
  return clone;
}

```
