---
title: Lync Server 2013：準備鎖定的 Active Directory 網域服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing a locked-down Active Directory Domain Services
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48184377
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b3e1eb33568bbc0e1742e31638a20879e4fffdd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513360"
---
# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a>在 Lync Server 2013 中準備鎖定的 Active Directory 網域服務

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-05-14_

組織通常會鎖定 Active Directory 網域服務，以協助降低安全性風險。 不過，鎖定的 Active Directory 環境可以限制 Lync Server 2013 所需的許可權。 正確準備 Lync Server 2013 的鎖定 Active Directory 環境時，包含一些額外的考慮和步驟。

鎖定的 Active Directory 環境是以下列兩種常見方式來限制權限：

  - 已驗證的使用者存取控制項目 (ACE) 已從容器中移除。

  - User、Contact、InetOrgPerson 或 Computer 物件的容器已停用權限繼承。

<div>

## <a name="in-this-section"></a>本節內容

  - [已在 Lync Server 2013 中移除已驗證的使用者許可權](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [已停用 Lync Server 2013 中電腦、使用者或 InetOrgPerson 容器的許可權繼承](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

