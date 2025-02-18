# Big Zip
Unzip this archive and find the flag.

- [Download zip file](https://artifacts.picoctf.net/c/503/big-zip-files.zip)
Can grep be instructed to look at every file in a directory and its subdirectories?

## Solucion
Con la terminal de kali linux

```
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills2]
└─$ unzip big-zip-files.zip         
Archive:  big-zip-files.zip
replace big-zip-files/jpvaawkrpno.txt? [y]es, [n]o, [A]ll, [N]one, [r]ename: A
 extracting: big-zip-files/jpvaawkrpno.txt  
  inflating: big-zip-files/oxbcyjsy.txt  
  inflating: big-zip-files/hllhxlvvdgiii.txt  
  inflating: big-zip-files/bdvnqbuutefealgveyiqd.txt  
  inflating: big-zip-files/fudfsewmaafsbniiyktzr.txt  
  inflating: big-zip-files/folder_fqmjtuthge/file_eaigogtrdslbxenbnfisxepj.txt  
  inflating: big-zip-files/folder_fqmjtuthge/file_ygocxgpzuxqjwfs.txt  
  inflating: big-zip-files/folder_fqmjtuthge/file_lqqprxhjtarithwygepdnlf.txt  
  inflating: big-zip-files/folder_fqmjtuthge/file_pdpygeaphbafepdzw.txt  
  inflating: big-zip-files/folder_fqmjtuthge/file_wwxeisxucykwqtkgcrkv.txt  
  inflating: big-zip-files/folder_fqmjtuthge/file_aowfebnypzsretakipi.txt  
  inflating: big-zip-files/folder_fqmjtuthge/file_jlfivzrgcubr.txt  
  inflating: big-zip-files/folder_fqmjtuthge/file_pnwvfhejwcqseezvmdv.txt  
  inflating: big-zip-files/folder_fqmjtuthge/file_lajnafrfzk.txt  
  inflating: big-zip-files/folder_fqmjtuthge/file_zqjgjdxgn.txt  
  inflating: big-zip-files/folder_fqmjtuthge/folder_woanzvubrt/file_ijoohrldnvltouiak.txt  
  inflating: big-zip-files/folder_fqmjtuthge/folder_woanzvubrt/file_killpqhviqfap.txt  
  inflating: big-zip-files/folder_fqmjtuthge/folder_woanzvubrt/file_hwenfgbvlsiutpzap.txt  
  inflating: big-zip-files/folder_fqmjtuthge/folder_woanzvubrt/file_zkjxknslrgiqbqhwvsfmns.txt  
  inflating: big-zip-files/folder_fqmjtuthge/folder_woanzvubrt/file_lmptznpgvygegty.txt  
  inflating: big-zip-files/folder_fqmjtuthge/folder_woanzvubrt/file_nrcepuoopamysxstrnwef.txt  
  inflating: big-zip-files/folder_fqmjtuthge/folder_woanzvubrt/file_cphxqwro.txt  
  inflating: big-zip-files/folder_fqmjtuthge/folder_woanzvubrt/file_zwqgrfamcujobfh.txt  
  inflating: big-zip-files/folder_fqmjtuthge/folder_woanzvubrt/file_sldobvymdlygz.txt  
  inflating: big-zip-files/folder_fqmjtuthge/folder_woanzvubrt/file_xpnrbselkyinkrfncbw.txt  
  inflating: big-zip-files/folder_fqmjtuthge/folder_woanzvubrt/file_rmdklobror.txt  
...
  inflating: big-zip-files/folder_oetovspdce/file_bhngwuoxvxmswhrbhe.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/gqcyepbiqxaaou.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/fldojuhvoksgzmvjui.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/file_yzszguvjqowihejtbczb.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/file_mdynxfbelqmkccuptpfvsx.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/zoyegjwhsekui.txt  
 extracting: big-zip-files/folder_wdhgdgrbfc/izpsdjrflyxcpuhjtaflbtp.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/fxaxiryjldhjugrsxhndjglp.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/file_qmzrrkkuaqnol.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/xktktzhdxnfu.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/puqtvrnhomqbrkguy.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/file_czpkyijqgdzhwkfkyd.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/ncpphsegf.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/rpagkqbzcuxepx.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/pdppdhedydlawgvhwym.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/qbwalzyyprvrcjpepe.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/file_ljeldszgyuc.txt  
 extracting: big-zip-files/folder_wdhgdgrbfc/lmjsuinfffmpmyjmmk.txt  
 extracting: big-zip-files/folder_wdhgdgrbfc/tdwocpenvymtoj.txt  
 extracting: big-zip-files/folder_wdhgdgrbfc/fdsjfllubxcxwhpv.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/file_jyvxtmmtpl.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/file_epcuiockebhmxxtago.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/tvnwbgmapeulf.txt  
 extracting: big-zip-files/folder_wdhgdgrbfc/finitvya.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/bondkyoxvdcgxyq.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/file_hacfyxtdwkdiycfwatiyvusg.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/file_jdlhinpycace.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/gnsnwwhmlslslscapr.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/file_ximyquuowm.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/siizcxeduftjnvian.txt  
  inflating: big-zip-files/mktyhgmedcj.txt  
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills2]
└─$ grep -r "pico" big-zip-files    
big-zip-files/folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}
```