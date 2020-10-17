---
title: 執行 LyncPerfTool
description: 執行 LyncPerfTool。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3278754c9154f47602c5c4f1fa95cdc4b465b228
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560079"
---
# <a name="run-lyncperftool"></a>執行 LyncPerfTool

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

在執行 Lync Server 2013 的壓力和效能工具之前 ( # A0) ，您必須建立使用者、連絡人及案例。 如需使用工具來執行這些動作的詳細資訊，請參閱 [建立使用者和連絡人](create-users-and-contacts.md) 及 [設定使用者設定檔](configure-user-profile.md)。 執行這些工具也會產生檔案，該檔案會在批次檔案中執行 LyncPerfTool.exe，並包含必要的參數。

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a>執行 Lync Server 2013 壓力和效能工具

UserProfileGenerator.exe 工具會建立批次處理檔案，可讓您註冊 LyncPerfTool 效能計數器及載入 XML 設定檔，以執行 LyncPerfTool.exe。 批次檔案會針對每個設定檔執行 LyncPerfTool.exe 的一個實例。 若要執行批次檔，請執行下列動作：

1.  將包含設定資料夾和檔案的資料夾，複製到每一部用戶端電腦上包含 LyncStressTool.exe 的目錄。  (例如，如果在名為 1.28 13.16.16 的資料夾中產生設定檔 \_ ，請將該資料夾複製到每個用戶端上包含 LyncPerfTool.exe 的資料夾。 ) 

2.  流覽至正確編號的用戶端資料夾，並執行 RunClient 批次腳本。 您只要按兩下 [Windows Explorer] 中的批次處理檔案，它就會執行該用戶端號碼的所有設定檔案。 您也可以使用下列語法，從適當的用戶端資料夾執行腳本：

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
若要直接執行 LyncPerfTool.exe，請開啟命令提示字元，然後在命令列中輸入下列命令 (當您第一次執行這項時，請務必註冊效能計數器 regsvr32/i/n/s LyncPerfToolPerf.dll，如本主題稍後的附注所示) # A2/file：\<configXML\>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
若要讓工具在設定檔中顯示值，請在前述命令上加入/displayfile 參數，如下所示：
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
若要結束進程，請按 Ctrl+C。

<div>


> [!NOTE]  
> 在直接執行 LyncPerfTool 之前，必須先註冊效能計數器。 輸入下列命令以註冊效能計數器：



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> 您啟動的每個 LyncPerfTool.exe 實例都會立即開始登入使用者，通常會以每秒一個使用者的速率來進行簽署。 集區的最高使用者登入率，每秒大約12個。 這表示您不應該同時啟動超過12個 LyncPerfTool 實例，而使用者仍在登入。 1000使用者大約需要20分鐘的時間來完全登入（每秒一個）。



</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[建立使用者和連絡人](create-users-and-contacts.md)  
[設定使用者設定檔](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

