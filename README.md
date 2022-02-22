# two usages
## ---compression---
1  ```cat ucsc.hg19.fasta | tr -d 'N' | tr 'acgt' 'ACGT' | grep -v '>' | head -n 1000000 | paste -sd '' >test.ACGT```  
  
2  ```<test.ACGT ACGT_2_ASCII```  
  
3  ```ASCII_2_ACGT | tee test.ACGT.0```  
  
4  ```diff test.ACGT test.ACGT.0```

Note: &nbsp; test.ACGT is a txt file with ACGT; &nbsp; all of three files(file0,file1,file2) is the compressed file; &nbsp; test.ACGT.0 is the decompressed file




      
       
## ---encryption---
1  ```echo "magnet:?xt=urn:btih:716c3dcd7d3b6c24efc6db32710849d40230fb4f&dn" >file0; echo >file1; echo >file2```  
  
2  ```ASCII_2_ACGT | tee 177.magnet.ACGT```  
  
3  ```rm file0; <177.magnet.ACGT ACGT_2_ASCII```  
  
4  ```cat file0```
  
Note: &nbsp; file0 is a txt file with printable characters; &nbsp; 177.magnet.ACGT is the encrypted file; &nbsp; file0 is the decrypted file
