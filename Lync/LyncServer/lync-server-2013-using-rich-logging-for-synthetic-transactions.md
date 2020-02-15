---
title: Lync Server 2013： 使用綜合交易的豐富記錄
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
ms.openlocfilehash: 421b691bd282b858eca64c9756e92dd24aac8b7b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a>使用 Lync Server 2013 中的綜合交易的豐富記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-22_

綜合交易 （Microsoft Lync Server 2010 中引進） 提供讓系統管理員來確認使用者能夠成功完成 [登入系統、 交換立即訊息，或撥打電話到位於電話等一般工作公用交換電話網路 (PSTN)。 可以手動進行這些測試 （這會封裝成一組 Lync Server Windows PowerShell cmdlet），由系統管理員，或他們可自動執行的應用程式，例如 System Center Operations Manager。

Lync Server 2010 中的綜合交易，證明中協助識別系統問題的系統管理員非常有用。 例如， **Test-csregistration** cmdlet 無法發出警示系統管理員一些使用者已有困難註冊搭配 Lync Server 的事實。 然而，如果綜合交易是比較沒有幫助判斷為什麼這些使用者已困難註冊搭配 Lync Server 系統管理員。 這已經因為綜合交易未提供可協助您遇到了 Lync Server 系統管理員的詳細的記錄資訊。 綜合交易的詳細資訊輸出充其量只能提供逐步資訊，讓系統管理員能夠根據經驗來猜測可能發生問題的地方。

在 [Microsoft Lync Server 2013，綜合交易都已重新架構提供豐富的記錄。 「豐富的記錄」表示將針對綜合交易所進行的每個活動記錄如下的資訊：

  - 活動開始時間

  - 活動完成時間

  - 已執行的動作 （例如，建立、 加入或離開會議; 登入 Lync Server; 傳送立即訊息; 等等）

  - 活動執行時所產生的資訊、詳細資料、警告或錯誤訊息

  - SIP 登錄訊息

  - 活動執行時所產生的例外狀況記錄或診斷碼

  - 執行活動的最終結果

這項資訊會自動產生每次執行綜合交易。 不過，資訊不會自動顯示，或儲存記錄檔。 相反地，手動執行的綜合交易的系統管理員可以使用之後包含 OutLoggerVariable 參數來指定的資訊會儲存在 Windows PowerShell 變數。 從那裡，系統管理員可以使用一組的方法，可讓他們儲存及/或 rtf 登入 [XML] 或 [HTML 格式的檢視。

例如，Lync Server 2010 管理員可能會使用類似下列的命令執行**Test-csregistration** cmdlet:

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

這些檔案然後可以使用 Internet Explorer、 Visual Studio 中或任何其他應用程式能夠開啟 HTML/XML 檔案來檢視。

綜合交易，從執行 System Center Operations Manager 中的內容會自動產生失敗這些記錄檔。 不過，如果執行作業失敗之前 Windows PowerShell 無法載入及執行綜合交易，就不產生這些記錄檔。

> [!IMPORTANT]  
> 根據預設，Lync Server 2013 會將記錄檔儲存至未共用資料夾。 若要讓這些記錄檔隨時都能存取，您應該共用此資料夾 (例如， \\ \\atl-watcher-001.litwareinc.com\WatcherNode。


</div>

</div>

</div>

</div>

