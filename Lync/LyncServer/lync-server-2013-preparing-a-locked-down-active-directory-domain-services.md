---
title: Lync Server 2013： 準備鎖定的 Active Directory 網域服務
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
ms.openlocfilehash: 6e57d982983bdd5ca0f85235cd44bc2fba5b1bf7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a>準備鎖定的 Active Directory 網域服務在 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-05-14_

組織通常會鎖定 Active Directory 網域服務，以協助降低安全性風險。 不過，在鎖定的 Active Directory 環境可以限制 Lync Server 2013 需要的權限。 適當地準備 Lync Server 2013 鎖定的 Active Directory 環境包括一些其他考量和步驟。

鎖定的 Active Directory 環境是以下列兩種常見方式來限制權限：

  - 已驗證的使用者存取控制項目 (ACE) 已從容器中移除。

  - User、Contact、InetOrgPerson 或 Computer 物件的容器已停用權限繼承。

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中移除已驗證的使用者權限](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [在電腦、 使用者或 Lync Server 2013 中的 InetOrgPerson 容器已停用權限繼承](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

