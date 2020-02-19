---
title: Lync Server 2013： 驗證 Office Web Apps Server 的設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c1cabdf03250a056c2fedaeb41e1f6839aea75a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a>驗證 Lync Server 2013 中的 Office Web Apps Server 的設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-04-22_

Office Web Apps Server 已新增至拓撲，並發佈該拓撲之後，您應該會看到兩個新 Lync Server 事件記錄檔中的事件記錄檔事件。 首先，您應該新增 LS 資料 MCU 事件 （事件識別碼 41034）;此事件會報告已探索到 Office Web Apps Server:

**發現 web 會議伺服器 Office Web Apps Server 時，已啟用 PowerPoint 內容。**

除了為，您應該會看到另一個 LS 資料 MCU （事件識別碼 41032） 報告事件的回 Office Web Apps Server Url。 例如，您應該會看到類似：

**Web 會議伺服器 Office Web Apps Server 探索作業順利完成。**

**Office Web Apps Server 內部簡報者] 頁面上：https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Office Web Apps Server 內部出席者頁面：https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Office Web Apps Server 外部簡報者] 頁面上：https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Office Web Apps Server 內部出席者頁面：https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

如果您看到的 41033 事件 id，表示該 Office Web Apps Server 探索 LS 資料 MCU 事件失敗。 在此情況下，Microsoft Lync Server 2013 會嘗試為探索新設定的 Office Web Apps Server 所需的次數。 探索程序便會重複替換失敗時您應該移除您的拓撲文件中的 Office Web Apps Server、 發佈更新過的拓撲，並再重試連線問題都已解決後，Office Web Apps Server 新增回拓撲。

如果 Office Web Apps Server 出現正確設定，且具有已辨識的探索程序可以確認 Office Web Apps Server 是否如預期藉由共用 PowerPoint 簡報的 Microsoft Lync 2013 用戶端對之間運作。 如果使用者 A 可以載入並顯示在 PowerPoint 簡報，並且使用者 B 可以再加入會議，請參閱該簡報使用 Office Web Apps Server。

即使 Office Web Apps Server 出現正確設定，您無法可能會收到錯誤訊息 「 一些共用功能是否因伺服器連線問題而無法使用 」 當您嘗試共用 PowerPoint 簡報。 如果您收到您應該重新啟動前端 （或多部伺服器） 與新的 Office Web Apps Server 相關聯的錯誤訊息。

</div>

<span> </span>

</div>

</div>

</div>

