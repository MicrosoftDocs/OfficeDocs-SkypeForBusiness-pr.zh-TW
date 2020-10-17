---
title: Lync Server 2013：授與許可權
description: Lync Server 2013：授與許可權。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bdb2b1ef39b85caa89c7597f455e6e4fc08e44e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554499"
---
# <a name="granting-permissions-in-lync-server-2013"></a>在 Lync Server 2013 中授與許可權

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-15_

針對安裝程式，您可以將許可權授與特定 Active Directory 組織單位 (OU) 的 RTCUniversalServerAdmins 通用群組，啟用該 OU 中 RTCUniversalServerAdmins 群組的成員，以在指定的網域中安裝 Lync Server 2013。 當您授與 OU 的許可權時，會授與下列許可權：

  - 讀取

  - 寫入

  - ReadSPN

  - WriteSPN

為了進行管理，您可以將許可權新增至指定的 Ou，使樹系準備建立的 RTC 通用群組成員可以存取 Ou，而不需要是 Domain Admins 群組的成員。 新增至指定 OU 的許可權，與 **Enable-CsAdDomain** Cmdlet 新增至電腦和使用者 OU 容器的許可權相同。

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中授與設定許可權](lync-server-2013-granting-setup-permissions.md)

  - [在 Lync Server 2013 中授與組織單位許可權](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

