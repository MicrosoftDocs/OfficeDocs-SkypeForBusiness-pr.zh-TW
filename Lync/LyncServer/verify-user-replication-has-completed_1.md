---
title: 確認已完成使用者複製
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13f4fbd2e0d0236f9dc404ffa84ab2f0ce385e2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>確認已完成使用者複製

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

當您執行**CsLegacyUser** Cmdlet 時，您可能會因 Active Directory 網域服務（AD DS）與 Lync Server 2013 資料庫之間的使用者資訊無法同步處理，而導致無法同步處理，因為初始複製不完整。 成功完成 Lync Server 2013 使用者複製程式服務的初始同步處理所需的時間，取決於託管在 Lync Server 2013 池之 Active Directory 林中的網網域控制站數目。 Lync server 2013 的使用者複製服務初始同步處理常式是在 Lync Server 2013 前端伺服器第一次啟動時進行。 之後，就會根據使用者複製程式間隔來同步處理。 完成下列步驟以驗證使用者複製已完成，然後再執行**CsLegacyUser** Cmdlet。

<div>

## <a name="to-verify-that-user-replication-has-completed"></a>驗證使用者複製已完成

1.  從 Lync Server 2013 前端伺服器，按一下 [**開始**] 功能表，然後按一下 [**執行**]。

2.  輸入**eventvwr.exe** ，然後按一下 **[確定]**。

3.  在事件檢視器中，按一下 [**應用程式和服務記錄**] 加以展開，然後選取 [Lync Server]。

4.  在 [**動作**] 窗格中，按一下 [**篩選目前的記錄**]。

5.  從 [**事件來源**] 清單中，按一下 [ **LS 使用者複製**]。

6.  在** \<所有事件識別碼\> **中輸入**30024** ，然後按一下 **[確定]**。

7.  在 [篩選的事件] 清單中的 [一般] 索引標籤上，尋找 **[** 使用者複製已成功完成] 的專案。

</div>

</div>

<span> </span>

</div>

</div>

</div>

