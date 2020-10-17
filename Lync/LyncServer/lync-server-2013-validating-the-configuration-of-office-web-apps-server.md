---
title: Lync Server 2013：驗證 Office Web Apps Server 的設定
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
ms.openlocfilehash: 0a33a5e9bb93371bdccac3c88b7a1c080e3efaa8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503680"
---
# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a>驗證 Lync Server 2013 中的 Office Web Apps Server 設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-04-22_

將 Office Web Apps Server 新增至拓撲之後，在發行該拓撲之後，您應該會在 Lync Server 事件記錄檔中看到兩個新的事件記錄事件。 首先，應新增 LS 資料 MCU 事件 (事件識別碼 41034) 。此事件會報告已探索到 Office Web Apps Server：

**已探索 Web 會議伺服器 Office Web Apps Server，PowerPoint 內容已啟用。**

除了該之外，您還應該看到另一個 LS 資料 MCU 事件， (事件識別碼 41032) ，以報告回 URLs 的 Office Web Apps Server。 例如，您應該會看到類似下列的內容：

**Web 會議伺服器 Office Web Apps Server discovery 已成功。**

**Office Web Apps Server 內部簡報者頁面： https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Office Web Apps Server 內部出席者頁面： https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Office Web Apps Server 外部簡報者頁面： https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Office Web Apps Server 內部出席者頁面： https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

如果您看到 LS 資料 MCU 事件，但事件識別碼為41033，表示 Office Web Apps Server discovery 失敗。 在此情況下，Microsoft Lync Server 2013 會視需要嘗試許多次數，以探索新設定的 Office Web Apps Server。 如果探索過程重複失敗，您應該移除拓撲檔中的 Office Web Apps Server、發佈更新的拓撲，然後在解決連接問題後，嘗試將 Office Web Apps Server 重新新增至拓撲。

如果 Office Web Apps Server 似乎已正確設定，且已被探索程式識別，您可以在一對 Microsoft Lync 2013 用戶端之間共用 PowerPoint 簡報，以確認 Office Web Apps Server 的運作方式如預期般運作。 如果使用者 A 可以載入及顯示 PowerPoint 簡報，而且使用者 B 可以加入會議，並查看該簡報之後，Office Web Apps Server 會正常運作。

即使已正確設定 Office Web Apps Server，當您嘗試共用 PowerPoint 簡報時，可能會收到錯誤訊息「某些共用功能因伺服器連線問題而無法使用」。 如果您收到該錯誤訊息，您應該重新開機前端伺服器 (或與新 Office Web Apps Server 關聯的伺服器) 。

</div>

<span> </span>

</div>

</div>

</div>

