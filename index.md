<body>
<br><br><br><br>
<h1>Shade Cipher Translator</h1>

-> Write symbols in the top box ╩╞Ξ╡═Ξ and letters in the bottom box! Unknown symbols/letters will show up as "_" :)
<br><br>
<h3>Message to be decoded:</h3>
    
    <input type="text" placeholder="Insert symbols..." id="top_input">
    <button type="button" onclick="decode_input()">Decode!</button>
    <br> <br>
    <div id="text_top">
    </div>
    
    <br><br>
    <h3>Message to be encoded:</h3>
    <input type="text" placeholder="Type something..." id="bot_input">
    <button type="button" onclick="encode_input()">Encode!</button>
    <br> <br>
    <div id="text_bot">
    </div>
    <br><br><br><br><br><br>
    Made by @Ken._. | Shadeboi
 
    <script>
        var dict = {
        '╡': "X", 
        "╢": "V", 
        "╖": "T", 
        '╕': "O", 
        "Ξ": "E",
        "║": "Z", 
        '╗': "Y", 
        "╝": "W", 
        "╘": "U", 
        "╜": "C", 
        "╛": "D", 
        "╞": "F", 
        '╟': "G", 
        "╚": "H", 
        "╔": "I", 
        "╩": "J", 
        "╦": "K", 
        "╠": "L", 
        '═': "M", 
        "╬": "N", 
        "╧": "B", 
        "╨": "P", 
        "╫": "Q", 
        '╤': "R", 
        "╥": "S", 
        "╙": "A", 
        " ": " ",
      }
      
        function decode_input(){
            var input = document.getElementById("top_input").value;
            let output = "";
            for (let i = 0; i < input.length; i++) {                                                              
              if ((input.charAt(i) in dict)) {output += dict[input.charAt(i)];} 
              else if ((/[a-zA-Z]/).test(input.charAt(i))){output += "_";}
              else{output += input.charAt(i);}                               
            }
            document.getElementById("text_top").innerHTML = "Decoded message: " + output;
        }
        
        function encode_input(){
        var input = document.getElementById("bot_input").value.toUpperCase();                                     
        let output = "";
            for (let i = 0; i < input.length; i++) {
              current_char = input.charAt(i)
              if(current_char == " "){output += " "}
              else if (getKeyByValue(dict, current_char)) {output += getKeyByValue(dict, current_char);} 
              else if((/[a-zA-Z]/).test(current_char)){output += "_";} 
              else{output += current_char;}
            }
        document.getElementById("text_bot").innerHTML = "Decoded message: " + output;
        }
        
                                             
        function getKeyByValue(object, value) {
          return Object.keys(object).find(key => object[key] === value);
        }
    </script> 
  </body>  


