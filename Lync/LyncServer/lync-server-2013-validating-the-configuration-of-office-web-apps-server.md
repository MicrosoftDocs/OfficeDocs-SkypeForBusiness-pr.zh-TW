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
ms.openlocfilehash: 541929233eff5e401b3998aa84e463e2640378c0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a>驗證 Lync Server 2013 中的 Office Web Apps Server 設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-04-22_

在已將 Office Web Apps 伺服器新增到拓撲之後，且在該拓撲發佈之後，您應該會在 Lync 伺服器事件日誌中看到兩個新的事件記錄事件。 首先，應該新增 LS 資料 MCU 事件（事件 ID 41034）;這個事件會報告已發現 Office Web Apps 伺服器：

**已發現 Web 會議 Server Office Web Apps Server，已啟用 PowerPoint 內容。**

此外，您還會看到另一個 [LS 資料 MCU] 事件（事件 ID 41032），該事件會傳回 Office Web Apps Server Url。 例如，您應該會看到類似以下的內容：

**網路會議服務器 Office Web Apps 伺服器探索已成功完成。**

**Office Web Apps Server 內部簡報者頁面：https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Office Web Apps 伺服器內部出席者頁面：https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Office Web Apps Server 外部簡報者頁面：https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Office Web Apps 伺服器內部出席者頁面：https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

如果您看到 LS 資料 MCU 事件，且事件 ID 為41033，表示 Office Web Apps Server 發現失敗。 在這種情況下，Microsoft Lync Server 2013 會根據需要嘗試許多次數，以探索新設定的 Office Web Apps 伺服器。 如果探索程式重複失敗，您應該從拓撲檔中移除 Office Web Apps 伺服器、發佈更新的拓撲，然後在連線問題解決之後，嘗試將 Office Web Apps 伺服器新增到拓撲結構。

如果 Office Web Apps 伺服器出現正確設定，且已被探索程式辨識，您可以在一對 Microsoft Lync 2013 用戶端之間共用 PowerPoint 簡報，以驗證 Office Web Apps 伺服器是否在正常運作。 如果使用者 A 可以載入並顯示 PowerPoint 簡報，而使用者 B 可以接著加入會議，然後查看該簡報，則 Office Web Apps Server 就能正常運作。

即使 Office Web Apps 伺服器的設定正確，您也可能會在嘗試共用 PowerPoint 簡報時，收到「由於伺服器連線問題，有些共用功能無法使用」錯誤訊息。 如果您收到該錯誤訊息，您應該重新開機與新的 Office Web Apps 伺服器相關聯的前端伺服器（或伺服器）。

</div>

<span> </span>

</div>

</div>

</div>

