# Uranus
## This is a UML mirror that uses Hydra Abstract Syntax that can plugin to Hydrarchy Docs
![94697398a57a8899bde53b63d9bb0a26](https://user-images.githubusercontent.com/107733608/174940420-f05fc3fd-460c-4811-884f-cf8fa736a0b6.jpg)

### The syntax for Hydra has to be declaritively pure for this to work both ways:
1. In otherwords the Uranus pipeline should be able to be reversed to be able to mirror itself. 
2. This means all your object and function declarations need to remain in a state that does not care about from whence they came.
3. Pure declarations can be declared and interpreted in any order without affecting other pure declarations to give rise to this effect.
4. Finally, associations can be interpreted sequentially for state machine declarations and sequential declarations
5. Diagrams can be built in layers and then re-orderd for sequential associations  
