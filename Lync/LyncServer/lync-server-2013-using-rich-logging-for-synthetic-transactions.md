---
title: Lync Server 2013：針對綜合交易使用豐富記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d73bfe085d34e536c5d3b44f1cacca8819de442
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518790"
---
# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a>在 Lync Server 2013 中使用綜合交易記錄的豐富記錄

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

綜合交易 (引進于 Microsoft Lync Server 2010 中) 提供一種方法，讓系統管理員確認使用者是否可以成功完成常見工作，例如登入系統、交換立即訊息，或撥打位於公用交換電話網路 (PSTN) 的電話。 這些測試 (會打包成一組 Lync Server Windows PowerShell Cmdlet) 可由系統管理員手動執行，也可以由系統 Center Operations Manager 等應用程式自動執行。

在 Lync Server 2010 中，已證實綜合交易非常有用，可協助系統管理員識別系統的問題。 例如， **Test-CsRegistration** 指令程式可能會提醒系統管理員某些使用者在使用 Lync Server 註冊時遇到問題。 不過，「綜合交易」在協助系統管理員決定這些使用者在使用 Lync Server 註冊時有困難的用處稍少。 這是因為綜合交易沒有提供詳細的記錄資訊，可協助管理員對 Lync Server 的問題進行疑難排解。 綜合交易的詳細資訊輸出充其量只能提供逐步資訊，讓系統管理員能夠根據經驗來猜測可能發生問題的地方。

在 Microsoft Lync Server 2013 中，綜合交易已重新設計為提供豐富的記錄功能。 「豐富的記錄」表示將針對綜合交易所進行的每個活動記錄如下的資訊：

  - 活動開始時間

  - 活動完成時間

  - 執行的動作 (例如，建立、加入或離開會議）;登入 Lync 伺服器;傳送立即訊息;以此類推) 

  - 活動執行時所產生的資訊、詳細資料、警告或錯誤訊息

  - SIP 登錄訊息

  - 活動執行時所產生的例外狀況記錄或診斷碼

  - 執行活動的最終結果

每次執行綜合交易時，會自動產生這項資訊。 不過，此資訊不會自動顯示或儲存至記錄檔。 相反地，手動執行綜合交易的系統管理員可以使用 OutLoggerVariable 參數來指定將儲存資訊的 Windows PowerShell 變數。 然後，系統管理員可以使用一組方法，讓他們能夠以 XML 或 HTML 格式儲存及/或查看 rtf 記錄。

例如，Lync Server 2010 系統管理員可能會使用類似下列的命令執行 **Test-CsRegistration** Cmdlet：

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

系統管理員可以選擇在他們選擇的變數名稱之後包含 OutLoggerVariable 參數：

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> 請不要在變數名稱的開頭加上 $ 字元。請使用像是 RegistrationTest 的變數名稱，而不要使用 $RegistrationTest。

上述命令輸出內容如下：

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

不過，系統會顯示更多關於此次失敗的詳細資訊，而不只是上述顯示的錯誤訊息。若要使用 HTML 格式存取該資訊，請使用類似下列的命令，以便將儲存於變數 RegistrationTest 中的資訊儲存至 HTML 檔案：

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

或者，您可以使用 ToXML() 方法，將資料儲存至 XML 檔案：

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

然後，您可以使用 Internet Explorer、Visual Studio 或任何其他能夠開啟 HTML/XML 檔案的應用程式來查看這些檔案。

在 System Center Operations Manager 內執行的綜合交易，會自動產生這些記錄檔失敗。 不過，如果執行失敗，Windows PowerShell 能夠載入並執行綜合交易，將不會產生這些記錄。

> [!IMPORTANT]  
> Lync Server 2013 預設會將記錄檔儲存至未共用的資料夾。 若要讓這些記錄立即可供存取，您應該共用此資料夾 (例如 \\ \\ atl-觀察程式-001 litwareinc。 com\WatcherNode。


</div>

</div>

</div>

</div>

