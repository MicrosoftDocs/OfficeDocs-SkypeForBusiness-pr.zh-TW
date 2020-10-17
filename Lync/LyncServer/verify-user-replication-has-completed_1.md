---
title: 確認已完成使用者複製
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e51ff7889b97a58298256cc1a1de3a5d4f901608
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518000"
---
# <a name="verify-user-replication-has-completed"></a>確認已完成使用者複製

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

在執行 **Move-CsLegacyUser** Cmdlet 時，您可能會因 Active Directory 網域服務 (AD DS) 和 Lync Server 2013 資料庫之間的使用者資訊而失敗，因為初始複寫不完整，所以您可能會遇到失敗。 成功完成 Lync Server 2013 User 複寫器服務的初始同步處理所需的時間，取決於主控 Lync Server 2013 集區之 Active Directory 樹系中主控的網域控制站數目。 當您第一次啟動 Lync Server 2013 前端伺服器時，就會發生 Lync Server 2013 使用者複寫器服務初始同步處理常式。 完成後，則是根據使用者複寫器間隔來進行同步化。 在執行 **Move-CsLegacyUser** Cmdlet 之前，請完成下列步驟來確認已完成使用者複寫。

<div>

## <a name="to-verify-that-user-replication-has-completed"></a>確認使用者複寫已完成

1.  在 Lync Server 2013 前端伺服器上，按一下 [ **開始** ] 功能表，然後按一下 [ **執行**]。

2.  輸入 **eventvwr.exe**，然後按一下 [確定]****。

3.  在事件檢視器中，按一下 [應用程式及服務記錄檔]**** 予以展開，然後選取 Lync Server。

4.  在 [動作]**** 窗格中，按一下 [篩選目前的記錄]****。

5.  在 [事件來源]**** 清單中，按一下 [LS 使用者複寫器]****。

6.  在 **\<All Event IDs\>** [輸入 **30024** ] 中，然後按一下 **[確定]**。

7.  在篩選後事件清單的 [一般]**** 索引標籤上，尋找有無任何項目指出使用者複寫成功的項目。

</div>

</div>

<span> </span>

</div>

</div>

</div>

