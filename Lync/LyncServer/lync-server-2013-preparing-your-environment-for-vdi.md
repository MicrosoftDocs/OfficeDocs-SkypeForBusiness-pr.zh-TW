---
title: Lync Server 2013：為 VDI 準備環境
description: Lync Server 2013：為 VDI 準備您的環境。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing your environment for VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205154(v=OCS.15)
ms:contentKeyID: 48185052
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e90b9e0f09d3082a28406f1a1dc715285ee4d7e3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579909"
---
# <a name="preparing-your-lync-server-2013-environment-for-vdi"></a>為 VDI 準備 Lync Server 2013 環境

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

若要準備 Lync VDI 外掛程式的環境，管理員必須執行下列步驟。

1.  在 [Lync Server 2013] 中，確定所有 VDI 使用者的 EnableMediaRedirection 都設為 TRUE。 如需詳細資訊，請參閱 [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) Cmdlet 及 [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) Cmdlet 的說明主題。

2.  在資料中心電腦上，安裝所有虛擬機器上的 Lync 2013 用戶端。

3.  在本機電腦上，安裝 Lync VDI 外掛程式。

</div>

<span> </span>

</div>

</div>

</div>

