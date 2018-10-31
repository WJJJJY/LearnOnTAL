<font size=5><b>Converting A Frozen Graph To UFF</b></font>

>  you can use the fllowing sample code to convert the *.pb* frozen graph to *.uff* format file:<br>
>  *<code>convert-to-uff tensorflow -o name_of_ouput_uff_file --input-file name_of_input_pb_file -O name_of_ouput_tensor</code>*<br><br>
>  you can list the TensorFlow layer:<br>
>  *<code>convert-to-uff tensorflow --input-file name_of_input_pb_file -l</code>*