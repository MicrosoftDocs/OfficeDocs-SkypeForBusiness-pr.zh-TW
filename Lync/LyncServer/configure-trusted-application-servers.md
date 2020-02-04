---
title: 設定信任的應用程式伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fee8a8894285a321a4a0bc51a7cdf0462be7af85
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>設定信任的應用程式伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-11_

在混合式環境中，如果您建立新的受信任的應用程式伺服器，您必須將下一個躍點池設定為 Lync Server 2013 池。 在混合式環境中，舊版 Lync Server 2010 池和 Lync Server 2013 池都會出現在下拉式清單中。 不支援選取舊版池。

**在建立信任的應用程式伺服器時，選取 Lync Server 2013 做為下一個躍點**

1.  開啟拓撲建立器。

2.  在左窗格中，以滑鼠右鍵按一下 [**受信任的應用程式伺服器**]，然後按一下 [**新增信任的應用程式**

3.  輸入受信任的應用程式池的 [**池 FQDN** ]，然後選取它將是單一伺服器或多重伺服器。

4.  按一下 **[下一步]**。

5.  在 [**選取下一個躍點]** 頁面上的清單中，選取 [Lync Server 2013 前端] 池。

6.  按一下 **[完成]**。

7.  選取頂端節點**Lync Server** ，然後從 [**動作**] 功能表選取 [**發佈**]。
    
    確認**信任的應用程式池**已順利建立，且與正確的前端池相關聯。

</div>

<span> </span>

</div>

</div>

</div>

