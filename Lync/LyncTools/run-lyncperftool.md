---
title: 執行 LyncPerfTool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: daf46c5e34558a719cdf4fafa15a57f273c4030d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-lyncperftool"></a>執行 LyncPerfTool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

在執行 Lync Server 2013 的應力和效能工具（LyncPerfTool）之前，您必須建立使用者、連絡人和案例。 如需使用工具執行這些動作的詳細資料，請參閱[建立使用者和連絡人](create-users-and-contacts.md)及[設定使用者設定檔](configure-user-profile.md)。 執行這些工具也會產生一個檔案，該檔案會以包含所需參數的批次檔案的一部分來執行 LyncPerfTool。

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a>執行 Lync Server 2013 應力和效能工具

UserProfileGenerator 工具會建立可讓您執行 LyncPerfTool 的批次處理檔案，方法是註冊 LyncPerfTool 效能計數器並載入 XML 設定檔。 批次處理檔案會針對每個設定檔執行 LyncPerfTool 的一個實例。 若要執行批次檔案，請執行下列動作：

1.  將包含配置資料夾和檔案的資料夾，複製到每個用戶端電腦上包含 LyncStressTool 的目錄。 （例如，如果您在名為 1.28\_13.16.16 的資料夾中產生了設定檔案，請將該資料夾複製到每個用戶端上包含 LyncPerfTool 的資料夾）。

2.  流覽至適當編號的用戶端資料夾，並執行 RunClient 批次腳本。 您只要在 Windows 資源管理器中按兩下批次檔案，該檔案就會針對該用戶端編號執行所有設定檔案。 您也可以使用下列語法，在適當的用戶端資料夾中執行腳本：

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
若要直接執行 LyncPerfTool，請開啟命令提示字元，然後在命令列中輸入下列命令（第一次執行此動作時，請務必註冊效能計數器 regsvr32/i/i/n LyncPerfToolPerf，如本主題稍後所示的筆記所示）： LyncPerfTool/file：\<configXML\>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
若要讓工具顯示設定檔中的值，請在前面的命令中包含/displayfile 參數，如下所示：
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
若要結束處理常式，請按 Ctrl + C。

<div>


> [!NOTE]  
> 在直接執行 LyncPerfTool 之前，您必須先註冊效能計數器。 輸入下列命令來註冊效能計數器：



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> 您開始的每個 LyncPerfTool 實例都會立即開始登入使用者，通常是每秒一個使用者的速率。 該池的使用者登入速率峰值，大約每秒12次。 這表示您不應該同時啟動超過12個 LyncPerfTool 實例，而使用者仍在登入。 1000使用者大約需要20分鐘的時間才能完全登入（每秒一個）。



</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[建立使用者和連絡人](create-users-and-contacts.md)  
[設定使用者設定檔](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

