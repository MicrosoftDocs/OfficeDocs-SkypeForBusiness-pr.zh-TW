---
title: Lync Server 2013：針對綜合交易使用豐富的記錄
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
ms.openlocfilehash: 48efc99a49fd41678d07eef8685bc7f045397aa3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a>在 Lync Server 2013 中使用 [綜合交易] 的豐富記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

綜合交易（在 Microsoft Lync Server 2010 中引進）提供一種方式，讓系統管理員確認使用者能夠成功完成一般工作，例如登入系統、交換立即訊息，或撥打電話給在公用交換電話網絡（PSTN）上。 這些測試（封裝為一組 Lync Server Windows PowerShell Cmdlet）可以由系統管理員手動執行，或由 System Center Operations Manager 等應用程式自動執行。

在 Lync Server 2010 中，綜合交易已證實在協助管理員找出系統問題時非常有用。 例如， **CsRegistration** Cmdlet 會提醒管理員，這是因為有些使用者難以在 Lync Server 註冊。 不過，綜合交易在協助管理員決定這些使用者為何無法使用 Lync Server 進行註冊，這種方式不太有用。 這是因為綜合交易不提供詳細的記錄資訊，可協助系統管理員針對 Lync Server 的問題進行疑難排解。 從綜合交易的詳細資料輸出中，提供的逐步資訊可能會讓系統管理員在可能的情況下，讓您有權猜到發生問題的位置。

在 Microsoft Lync Server 2013 中，已重新設計綜合交易來提供豐富的記錄。 "豐富記錄" 代表，對於綜合交易 undertakes 的每個活動，都會錄製如下的資訊：

  - 活動開始的時間

  - 活動的完成時間

  - 所執行的動作（例如，建立、加入或離開會議; 登入 Lync Server; 傳送即時消息; 等等）

  - 當活動執行時產生的資訊、詳細、警告或錯誤訊息

  - SIP 註冊訊息

  - 在活動執行時產生的例外記錄或診斷程式代碼

  - 執行活動的最終結果

這項資訊會在每次執行綜合交易時自動產生。 不過，資訊不會自動顯示或儲存至記錄檔。 相反地，手動執行綜合交易的系統管理員可以使用 OutLoggerVariable 參數來指定要儲存資訊的 Windows PowerShell 變數。 然後，管理員就可以使用一組方法，讓他們以 XML 或 HTML 格式儲存及/或查看豐富記錄。

例如，Lync Server 2010 系統管理員可以使用類似下列的命令來執行**CsRegistration** Cmdlet：

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

系統管理員可以選擇包含 OutLoggerVariable 參數，後面接著其選擇的變數名稱：

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> 請勿在變數名稱前面加上 $ 字元。 使用變數名稱（例如 RegistrationTest，而非 $RegistrationTest）。

上述命令會輸出如下所示的內容：

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

不過，這項失敗的詳細資訊比上述所示的錯誤訊息更多。 若要以 HTML 格式存取該資訊，請使用類似以下的命令，將儲存在可變 RegistrationTest 中的資訊儲存為 HTML 檔案：

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

或者，您也可以使用 ToXML （）方法將資料儲存至 XML 檔案：

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

然後，您就可以使用 Internet Explorer、Visual Studio 或任何能夠開啟 HTML/XML 檔案的任何其他應用程式來查看這些檔案。

從系統中心作業管理員內部執行的綜合交易，會自動產生這些記錄檔案，以尋找失敗。 不過，如果在 Windows PowerShell 能夠載入並執行綜合交易之前執行失敗，就不會產生這些記錄。

> [!IMPORTANT]  
> 根據預設，Lync Server 2013 會將記錄檔案儲存到未共用的資料夾中。 若要讓這些記錄易於存取，您應該共用此資料夾（例如\\ \\atl-觀察程式-001. litwareinc. com\WatcherNode。


</div>

</div>

</div>

</div>

