## Change Show / Hidden Element     

    <div class="row">    
    Type
        <select name="type" id="type" style="margin-left:57px; width:153px;">
                <option ame="l_letter" value="l_letter">Large Letter</option>
                <option name="letter" value="letter">Letter</option>
                <option name="parcel" value="parcel">Parcel</option>
        </select>                    
    </div>

    <div class="row" id="row_dim">
        Dimensions
        <input type="text" name="length" class="dimension" placeholder="Length">
        <input type="text" name="width" class="dimension" placeholder="Width">
        <input type="text" name="height" class="dimension" placeholder="Height">
    </div>

    <script>
        $(function() {
            $('#row_dim').hide(); 
            $('#type').change(function(){
                if($('#type').val() == 'parcel') {
                    $('#row_dim').show(); 
                } else {
                    $('#row_dim').hide(); 
                } 
            });
        });
    </script>

[Test Code](http://jsfiddle.net/Y3pW9/926/)    