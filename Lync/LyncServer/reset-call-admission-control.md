---
title: 重設通話許可控制
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6956b1a871a4a0a5c7e758d2890a58989f5ac8a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a>重設通話許可控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-11_

如果 Lync Server 2010 前端池是託管呼叫許可控制（CAC），您必須先將 CAC 主機託管到 Lync Server 2013 池，才能移除 Lync Server 2010 前端池。

<div>

## <a name="to-reset-cac"></a>若要重設 CAC

1.  開啟拓撲建立器。

2.  以滑鼠右鍵按一下網站節點，然後按一下 [**編輯屬性**]。

3.  在 [**呼叫許可控制設定**] 底下，請確認已選取 [**啟用撥號許可控制**]。

4.  在 [前端池] 底下，**若要執行 [呼叫許可控制] （CAC）**，請選取要裝載 CAC 的 Lync Server 2013 池，然後按一下 **[確定]**。

5.  發佈拓撲。

</div>

</div>

<span> </span>

</div>

</div>

</div>

