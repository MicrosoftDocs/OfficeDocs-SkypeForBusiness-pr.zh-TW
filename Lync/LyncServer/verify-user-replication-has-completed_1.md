---
title: 確認使用者複寫已完成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6433c1e88edf69b957047b9dc405df392e5ec104
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>確認使用者複寫已完成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-28_

當執行**Move-cslegacyuser** cmdlet，您可能會遇到失敗，因為 Active Directory 網域服務 (AD DS) 和正在不同步，因為在初始複寫不完整的 Lync Server 2013 資料庫之間的使用者資訊。 Lync Server 2013 使用者複寫器服務的初始同步處理成功完成所需時間取決於裝載在主控的 Lync Server 2013 集區的 Active Directory 樹系中的網域控制站的數目。 Lync Server 2013 Front End Server 第一次啟動時，就會發生的 Lync Server 2013 使用者複寫器服務初始同步處理程序。 完成後，則是根據使用者複寫器間隔來進行同步化。 在執行 **Move-CsLegacyUser** Cmdlet 之前，請完成下列步驟來確認已完成使用者複寫。

<div>

## <a name="to-verify-that-user-replication-has-completed"></a>確認使用者複寫已完成

1.  從 Lync Server 2013 前端伺服器中，按一下 [**開始**] 功能表，然後按一下 [**執行**。

2.  輸入 **eventvwr.exe**，然後按一下 [確定]****。

3.  在事件檢視器中，按一下 [應用程式及服務記錄檔]**** 予以展開，然後選取 Lync Server。

4.  在 [動作]**** 窗格中，按一下 [篩選目前的記錄]****。

5.  在 [事件來源]**** 清單中，按一下 [LS 使用者複寫器]****。

6.  在 [**\<所有的事件識別碼\>** 輸入**30024** ，然後按一下 [**確定]**。

7.  在篩選後事件清單的 [一般]**** 索引標籤上，尋找有無任何項目指出使用者複寫成功的項目。

</div>

</div>

<span> </span>

</div>

</div>

</div>

