---
title: 設定信任的應用程式伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92e7f2c808e9ea5a3e8dfbf3010715c86e02596e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>設定信任的應用程式伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

在混合式環境中，如果您在將舊版 Office 通訊伺服器拓朴與 Lync Server 2013 合併之後建立新的受信任的應用程式伺服器，而您使用 [拓撲建立器] 來定義新的信任應用程式伺服器，則您必須將下一個躍點池設定為Lync Server 2013 pool。 在合併的環境中，舊版 Office 通訊伺服器池和 Lync Server 2013 池都會出現在下拉式清單中。 *不*支援選取舊版池。

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a>在建立受信任的應用程式伺服器時，選取 Lync Server 2013 做為下一個躍點

1.  在拓撲建立器中開啟現有的拓撲。

2.  在左窗格中，以滑鼠右鍵按一下 [**受信任的應用程式伺服器**]，然後按一下 [**新增信任的應用程式**

3.  輸入受信任的應用程式池的 [**池 FQDN** ]，然後選取它將是單一伺服器或多重伺服器部署。

4.  按一下 **[下一步]**。

5.  在 [**選取下一個躍點]** 頁面上的清單中，選取 [Lync Server 2013 前端] 池。
    
    ![[定義新信任的應用程式集區] 對話方塊](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "[定義新信任的應用程式集區] 對話方塊")  

6.  按一下 **[完成]**。

7.  選取頂端節點**Lync 伺服器**，然後從 [**動作**] 窗格中，選取 [**發佈**]。

8.  驗證**受信任的應用程式池**已成功建立，且與正確的 [前端] 池相關聯。

</div>

</div>

<span> </span>

</div>

</div>

</div>

