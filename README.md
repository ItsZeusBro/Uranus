# Uranus
## Uranus is an Abstract Diagram Syntax which plugs in to Hydra.
#### It produces UML diagrams in the Uranus Server and in Hydrarchy's Documentation if Hydrarchy's plugin is included. 

![94697398a57a8899bde53b63d9bb0a26](https://user-images.githubusercontent.com/107733608/174940420-f05fc3fd-460c-4811-884f-cf8fa736a0b6.jpg)


  

### Diagram Symbols for Uranus Plugin

|   **Associations**   |                    **Dotted Line**                   |                   **Solid Line**                   |                             |                             |
|:--------------------:|:----------------------------------------------------:|:--------------------------------------------------:|:---------------------------:|:---------------------------:|
|                      |                           -                          |                          _                         |                             |                             |
|    **Arrowheads**    |                       **Open**                       |                     **Closed**                     |           **Open**          |          **Closed**         |
|                      |                           >                          |                         >>                         |              <              |              <<             |
|    **Interfaces**    |                  **Ball and Socket**                 |                 **Ball and Socket**                |          **Ports**          |                             |
|                      |                         -(*-                         |                        -*)-                        |              []             |                             |
|    **Composition**   |              **Dotted Line Composition**             |             **Dotted Line Composition**            | **Closed Line Composition** | **Closed Line Composition** |
|                      |                         <>-                          |                         -<>                        |              _<>            |             <>_             |
|  **Starting State**  |              **Starting State or Ball**              |                                                    |                             |                             |
|                      |                           *                          |                                                    |                             |                             |
|   **Ending State**   |           **Ending State or Enclosed Ball**          |                                                    |                             |                             |
|                      |                          (*)                         |                                                    |                             |                             |
|    **Entry Point**   |            **Entry Point or Flow Element**           |                                                    |                             |                             |
|                      |                         (><)                         |                                                    |                             |                             |
|      **Choice**      |      **Just use Chevrons to create the Diamond**     |                                                    |                             |                             |
|                      |                          <>                          |                                                    |                             |                             |
|    **Destruction**   |             **Destructive Associations**             | **Add text fields to Destructive Associations**    |                             |                             |
|                      |                     -X- or -X-X-                     |              -()-X-()- or -()-(X)-()-              |                             |                             |
|       **Actor**      |               **Stick figgure person**               |                                                    |                             |                             |
|                      |                        *-\|-<                        |                                                    |                             |                             |
|       **Fork**       |   Dotted Line going in, Two Dotted Lines going out   |   Solid Line going in, Two Solid Lines going out   |                             |                             |
|                      |                         -\|=                         |                        _\|=                        |                             |                             |
|       **Join**       | Two Dotted Lines going in, One Dotted Line going out | Two Solid Lines going in, One Solid Line going out |                             |                             |
|                      |                         =\|-                         |                        =\|_                        |                             |                             |
| **Send and Recieve** |                       **Send**                       |                     **Recieve**                    |                             |                             |
|                      |                         \|=>                         |                        <=\|                        |                             |                             |
|      **Package**     |                                                      |                                                    |                             |                             |
|                      |                          [^]                         |                                                    |                             |                             |
|       **Note**       |                                                      |                                                    |                             |                             |
|                      |                          [v]                         |                                                    |                             |                             |
|  **Shallow History** |                                                      |                                                    |                             |                             |
|                      |                          (H)                         |                                                    |                             |                             |
|       **Oval**       |                                                      |                                                    |                             |                             |
|                      |                          ()                          |                                                    |                             |                             |
|       **Node**       |                                                      |                                                    |                             |                             |
|                      |                       [[[]]]                         |                                                    |                             |                             |
|       **Rectangle**  |                                                      |                                                    |                             |                             |
|                      |                         [[]]                         |                                                    |                             |                             |

## Basic Example:
    //Uranus syntax in hydra file
    {
      {
        objName1:{
          sym: [[]],
          ass:[
            {
              sym: ("1")->>,
              to: objName2 
            },
            {
              sym: ("1..2")_>>,
              to: objName3
            }
          ]
        }
      },
      {
        objName2:{
          sym: [[]],
          ass:[
            {
              sym: ("1..n")-("<<strong like bull>>")->,
              to: objName1 
            },
            {
              sym: ("2..3")_>,
              to: objName3
            }
          ]
        }
      },

        objName3:{
          sym: [[]],
          ass:[
            {
              sym: ("1")_,
              to: objName1 
            },
            {
              sym: ("2")_>>,
              to: objName2
            }
          ]
        }
      }
    }
    
    //Native Hydra Objects
    {
      objName1:{
        type: "Class",
        props:{
          size: "10",
          desc: "small thing"
        },
        methods:{
          size: get_size()

        }
        
      },
      objName2:{
        type: "Class",
        props:{
          size: "14",
          desc: "strong thing"
        },
        methods:{
          strength: get_strength()
        }
      },
      objName3:{
        type: "Class",
        props:{
          size: "18",
          desc: "weighty thing"
        },
        methods:{
          weight: get_weight()
        }
      }
      
    }
