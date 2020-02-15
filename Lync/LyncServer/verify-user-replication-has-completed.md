---
title: 確認使用者複寫已完成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35e6cde338c4469cc7a04452cdf03fe87077d89f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>確認使用者複寫已完成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-17_

當執行**Move-csuser** cmdlet，您可能會遇到失敗，因為 Active Directory 網域服務 (AD DS) 和 Lync Server 2013 資料庫之間的使用者資訊是不同步，因為在初始複寫不完整。 Lync Server 2013 使用者複寫器服務的初始同步處理成功完成所需時間取決於裝載在主控的 Lync Server 2013 集區的 Active Directory 樹系中的網域控制站的數目。 Lync Server 2013 Front End Server 第一次啟動時，就會發生的 Lync Server 2013 使用者複寫器服務初始同步處理程序。 完成後，則是根據使用者複寫器間隔來進行同步化。 在執行 **Move-CsUser** Cmdlet 之前，請完成下列步驟來確認已完成使用者複寫。

<div>

## <a name="to-verify-user-replication-has-completed"></a>確認使用者複寫已完成

1.  以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。

2.  按一下 [開始]**** 功能表，然後按一下 [執行]****。

3.  輸入 **eventvwr.exe**，然後按一下 [確定]****。

4.  在事件檢視器中，按一下 [應用程式及服務記錄檔]**** 予以展開，然後選取 Lync Server。

5.  在 [動作]**** 窗格中，按一下 [篩選目前的記錄]****。

6.  在 [事件來源]**** 清單中，按一下 [LS 使用者複寫器]****。

7.  在 [**\<所有的事件識別碼\>** 輸入**30024** ，然後按一下 [**確定]**。

8.  在篩選後事件清單的 [一般]**** 索引標籤上，尋找有無任何項目指出使用者複寫成功的項目。

</div>

</div>

<span> </span>

</div>

</div>

</div>

