---
title: Lync Server 2013： 授與權限
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
ms.openlocfilehash: 495b556254ab42270aa031861aea0c4390f17602
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a>授與 Lync Server 2013 中的權限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012 年 10 月 15_

安裝程式，您可以授與權限的 RTCUniversalServerAdmins 萬用群組特定 Active Directory 組織單位 (OU)，讓該 OU 中指定的網域安裝 Lync Server 2013 中的 RTCUniversalServerAdmins 群組的成員。 當您授與 OU 權限時，會授與下列權限：

  - 讀取

  - 寫入

  - ReadSPN

  - WriteSPN

管理，您可以指定 ou 新增權限，使樹系準備所建立的 RTC 萬用群組的成員能夠存取 Ou，而不需要成為 Domain Admins 群組的成員。 新增至所指定 OU 權限是相同的權限**Enable-csaddomain** cmdlet 新增至電腦和使用者的 OU 容器。

<div>

## <a name="in-this-section"></a>本章節內容

  - [授與 Lync Server 2013 中的設定權限](lync-server-2013-granting-setup-permissions.md)

  - [授與 Lync Server 2013 中的組織單位權限](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

