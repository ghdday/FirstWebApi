using ArteMovels.Models;

namespace ArteMovels.Service;

public static class MovelService
{
    static List<Movel> Movels { get; }
    static int nextId = 3;
    static MovelService()
    {
        Movels = new List<Movel>
        {
            new Movel { id = 1, Name = "Cozinha Completa", OrçamentoFree = false },
            new Movel { id = 2, Name = "Banheiro",OrçamentoFree  = true }
        };
    }

    public static List<Movel> GetAll() => Movels;
    public static Movel? Get (int id) => Movels.FirstOrDefault(m =>m.id ==id);
      public static void Add(Movel movel)
    {
        movel.id = nextId++;
        Movels.Add(movel);
    }
public static void Delete(int id)
{
    var movel = Get (id);
    if (movel is null)
    return;
Movels.Remove(movel);
}
  
    public static void Update (Movel movel )
    {
        var index = Movels.FindIndex(m=> m.id == movel.id);
        if (index == -1)
        return;
        Movels[index] = movel;
    }
}
