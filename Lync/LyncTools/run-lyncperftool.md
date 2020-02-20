---
title: 執行 LyncPerfTool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5325a3dab058132dfe6bbf8558ebe771450f36ac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-lyncperftool"></a>執行 LyncPerfTool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-24_

在執行之前 [Lync Server 2013 壓力及效能工具 (LyncPerfTool.exe)，您必須建立使用者、 連絡人及案例。 如需使用工具來執行這些動作的詳細資訊，請參閱[建立使用者和連絡人](create-users-and-contacts.md)和[設定使用者設定檔](configure-user-profile.md)。 執行這些工具也會產生檔案所用執行身分批次檔案的一部分的 LyncPerfTool.exe 包含必要參數。

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a>執行 Lync Server 2013 壓力及效能工具

UserProfileGenerator.exe 工具建立批次檔案，可讓您執行 LyncPerfTool.exe 註冊 LyncPerfTool 效能計數器和載入 XML 組態檔。 批次檔案執行每個設定檔 LyncPerfTool.exe 一個執行個體。 若要執行的批次檔案，請執行下列動作：

1.  複製資料夾包含的設定資料夾和檔案至 LyncStressTool.exe 包含每個用戶端電腦的目錄。 (例如，如果名為 1.28 資料夾中產生的組態檔\_13.16.16，將該資料夾複製到包含 LyncPerfTool.exe 每個用戶端的資料夾。)

2.  瀏覽至適當編號的用戶端資料夾並執行 RunClient 批次指令碼。 您可以只連按兩下 [Windows 檔案總管] 中的批次檔案，它會執行所有的組態檔，該用戶端數目。 您也可以從適當的用戶端資料夾執行指令碼，使用下列語法：

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
若要直接執行 LyncPerfTool.exe，開啟命令提示字元，則請在命令列輸入下列命令 (當第一次這麼做，請務必將註冊為稍後此 topic):LyncPerfTool.exe /file 附註中顯示的效能計數器 regsvr32 /i /n /s LyncPerfToolPerf.dll，：\<configXML\>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
若要有工具顯示設定檔案中的值會包含 /displayfile 參數在上述命令，就像這樣：
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
若要結束程序，請按 Ctrl + C。

<div>


> [!NOTE]  
> 在執行之前 LyncPerfTool 直接，您必須註冊的效能計數器。 輸入下列命令，以登錄效能計數器：



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> 每個執行個體開始的 LyncPerfTool.exe 會立即啟動登入使用者，通常是一位使用者每秒的速率。 尖峰使用者登入率的集區是大約每秒的 12。 這表示，您應該不啟動超過 12 個 LyncPerfTool 執行個體同時，雖然使用者仍登入。 1000 個使用者將會完全在一秒登入，需要約 20 分鐘。



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

