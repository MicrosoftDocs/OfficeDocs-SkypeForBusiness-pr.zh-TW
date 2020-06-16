---
title: 設定信任的應用程式伺服器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: eb71833e782378f0d959fcbfcf5647235252e594
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>設定信任的應用程式伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-11_

在混合環境中，如果您建立新的受信任應用程式伺服器，則必須將下一個躍點集區設定為 Lync Server 2013 集區。 在混合環境中，舊的 Lync Server 2010 集區和 Lync Server 2013 集區會出現在下拉式清單中。 但不支援選取舊版集區。

**在建立信任的應用程式伺服器時，選取 [Lync Server 2013] 做為下一個躍點**

1.  開啟拓撲產生器。

2.  在左側窗格中，用滑鼠右鍵按一下 **[信任的應用程式伺服器]**，然後按一下 **[新增信任的應用程式集區]**。

3.  輸入信任的應用程式集區的 [**集區 FQDN** ]，並選取其將為單一伺服器或多部伺服器。

4.  按 [下一步]****。

5.  在 [**選取下一個躍點]** 頁面上，從清單中選取 [Lync Server 2013 前端集區]。

6.  按一下 [完成]****。

7.  選取頂端節點 [ **Lync Server** ]，然後從 [**動作**] 功能表中選取 [**發佈**]。
    
    確認已成功建立**信任的應用程式集**區，且該集區與正確的前端集區相關聯。

</div>

<span> </span>

</div>

</div>

</div>

