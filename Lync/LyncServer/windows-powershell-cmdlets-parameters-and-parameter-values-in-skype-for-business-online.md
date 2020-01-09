---
title: 商務用 Skype Online 中的 Windows PowerShell Cmdlet、參數及參數值
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9e9582941b05a4151be5baa2ce74acfc79b3db3
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a>商務用 Skype Online 中的 Windows PowerShell Cmdlet、參數及參數值

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-05_

如果您熟悉在所有 Windows 版本（或您熟悉 MS-DOS）中找到的命令視窗，當您瞭解如何使用 Windows PowerShell 時，就會開始進行。 在命令視窗中，您可以輸入命令，然後按 ENTER 鍵。 在 [回應] 中，電腦會執行命令或可執行檔。 例如，若要傳回目前目錄中所有檔案和資料夾的相關資訊，請在命令提示字元輸入這個命令，然後按 ENTER：

    dir

接著，您會傳回目前目錄中所有檔案和資料夾的相關資訊：

``` 
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/13/2013  02:53 PM                 117   pldok.log
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/21/2013  03:37 PM            207   setup.doc
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

當您只輸入命令或可執行檔的名稱時，這就是結果的一個範例。 不過，在命令視窗中執行的許多命令也會接受*引數*。 引數是傳遞至命令的其他資訊，可修改命令的行為。 例如，如果您只想在目前目錄中看到檔案和資料夾的名稱，就不會有其他資訊（例如檔案或資料夾的大小），或是資料夾或資料夾的建立日期和時間。 在這種情況下，執行 dir 命令時，會附加 **/b**引數：

    dir /b

當您包含 **/b**引數時， **dir**命令只會傳回目前目錄中所找到之資料夾和檔案的名稱：

    Deploy
    Intel
    PerfLogs
    Program Files
    Program Files (x86)
    Users
    Windows
    pldok.log
    RHDSetup.exe
    setup.doc

在上述命令中， **/b**引數是將傳回的資料限制為檔案和資料夾名稱所需的唯一資訊。 使用命令列命令時，通常會發生這種情況：只是變更命令列為所需的引數狀態。 （也就是說，您包含 **/b**引數以隱藏其他資訊，或排除 **/b**引數以顯示額外的資訊。）不過，在其他時間，您必須指定*引數值*。 引數值是傳遞給引數本身的其他資訊。 例如， **/o**引數可讓您指定 dir 命令排序傳回資料的方式。 在其他選項中，您可以使用引數值**e**來依據檔案副檔名或引數值**s**來排序（依檔案大小排序）。 例如，這個命令會依副檔名來排序傳回的資料。 請注意在 **/o**引數後面立即包含引數值**e**的方式：

    dir /oe

使用我們的範例資料夾，傳回的資料看起來會像這樣，而這些檔案會依副檔名字母順序排序：

``` 
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/21/2013  03:37 PM            207   setup.doc
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/13/2013  02:53 PM                 117   pldok.log
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

或者，協助您精確找出我們所談論的專案：

setup.exe. **核查**  
RHDSetup. **at.exe**  
pldok. **記錄**

雖然 Windows PowerShell 使用不同的術語，但使用 Windows PowerShell 的基本方法與使用命令視窗相同：您可以輸入命令，視需要包含引數和引數值，然後按 ENTER 執行這些命令。 不過請注意，Windows PowerShell 所使用的術語與命令外殼程式使用的不同。 在 Windows PowerShell 中，您執行的命令稱為*Cmdlet*。 接著，傳遞到 Cmdlet 的引數稱為*參數*，傳遞給參數的值稱為*參數值*。

前面的定義比較簡單。 Cmdlet 實質上是迷你應用程式，只能在 Windows PowerShell 環境中執行。 不過，您也可以在 Windows PowerShell 中執行其他命令和應用程式，包括大多數可從命令視窗執行的命令和應用程式。 例如，如果您想要從 Windows PowerShell 中啟動記事本，您只需輸入以下內容，然後按 ENTER 鍵：

    notepad.exe

不過，在管理商務用 Skype Online 時，大部分的系統管理員都會依賴 Windows PowerShell Cmdlet 來執行系統管理工作。 一次，有幾種其他類型的命令或應用程式可用來管理商務用 Skype Online。 有時候，您不需要任何其他引數就能使用商務用 Skype Online Cmdlet （如所述，引數稱為 Windows PowerShell 中的參數）。 例如，下列命令會呼叫不含任何其他參數的[CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) Cmdlet。 根據其本身，該命令會傳回您所有商務用 Skype Online 使用者的相關資訊：

    Get-CsOnlineUser

不過，大部分的商務用 Skype Online Cmdlet 也會接受參數（和參數值）。 請考慮下列命令：

    Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"

這個命令包含三個部分：

  - Cmdlet **CsOnlineUser**。

  - 身分識別參數。 請注意，在 Windows PowerShell 中，參數總是以破折號（-）開頭。 也就是說，對於這個相同的 Cmdlet，會使用下列語法來指示 UnassignedUser 參數：
    
        -UnassignedUser
    
    這個方法很有用，不只是因為參數必須以破折號開頭，也可能是因為這與命令視窗不同，其中的引數是使用正斜線（/）開頭的：
    
    ```console 
    /b
    ```

  - 參數值**kenmyer@litwareinc.com**。

這個指令會傳回特定使用者的相關資訊： kenmyer@litwareinc.com 身分識別的使用者。

<div>

## <a name="see-also"></a>請參閱


[Windows PowerShell 與 Lync Online 的簡介](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

