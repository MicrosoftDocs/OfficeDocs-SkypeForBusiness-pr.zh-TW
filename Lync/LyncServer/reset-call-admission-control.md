---
title: 重設通話許可控制
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f22f26ae48835dee6028e5b41b79dd116d610a25
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529810"
---
# <a name="reset-call-admission-control"></a>重設通話許可控制

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-11_

如果 Lync Server 2010 前端集區裝載通話許可控制 (CAC) ，您必須將 CAC 主控裝載至 Lync Server 2013 集區，才能移除 Lync Server 2010 前端集區。

<div>

## <a name="to-reset-cac"></a>重設 CAC

1.  開啟拓撲產生器。

2.  以滑鼠右鍵按一下網站節點，然後按一下 **[編輯屬性]**。

3.  在 **[通話許可控制設定]** 下方，確定已選取 **[啟用通話許可控制]**。

4.  在 [前端集區] 下， ** (CAC) **中，選取要裝載 CAC 的 Lync Server 2013 集區，然後按一下 **[確定]**。

5.  發行拓撲。

</div>

</div>

<span> </span>

</div>

</div>

</div>

