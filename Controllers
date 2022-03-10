using Microsoft.AspNetCore.Mvc;
using ArteMovels.Models;
using ArteMovels.Service;

namespace ArteMovels.Controllers;
[ApiController]
[Route("[Controller]")]

public class MovelsControllers : ControllerBase
{
    public MovelsControllers()
    {
    }
    [HttpGet]
    public ActionResult<List<Movel>>GetAll() =>
    MovelService.GetAll();
    
    [HttpGet("{id}")]
    public ActionResult<Movel>Get (int id)
    {
      var movel = MovelService.Get(id);
      if(movel== null)
        return NotFound();
          return movel;
    }

    [HttpPost] 
    public IActionResult Create (Movel movel)
    {
        MovelService.Add(movel);
        return CreatedAtAction(nameof(Create),new{id=movel.id},movel);
    }

    [HttpPut("{id}")]
    public IActionResult Update (int id ,Movel movel) 
    {
        if (id !=movel.id)
        return BadRequest();
        
        var existingMovel = MovelService.Get(id);
        if(existingMovel is null)
        return NotFound();
        
        MovelService.Update(movel);
        return NoContent();
    }


    [HttpDelete("{id}")]
    public IActionResult Delete (int id )
    {  
        var movel = MovelService.Get(id);
        if (movel is null) 
        return NotFound();

        MovelService.Delete(id); 
        return NoContent();
    }

}
