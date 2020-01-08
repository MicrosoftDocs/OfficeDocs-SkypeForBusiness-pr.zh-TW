---
title: Lync Server 2013：新增自訂文字到立即訊息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb6746ea5897d779a202bc428b6c7259a1191f6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a>在 Lync Server 2013 中新增自訂文字到立即訊息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

在每個 Lync 2013 立即訊息（IM）交談的開頭，使用**新的 CSClientPolicy**或 CSClientPolicy 的 Lync Server Management Shell Cmdlet （含 IMWarning 參數 **）** ，將免責聲明或警告新增到其中。

下列範例中的命令會在您每次開始新的 IM 交談時，在 [交談] 視窗的頂端新增安全性提醒：

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

使用**授與 CSClientPolicy**將此新原則指派給使用者。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的**新 CSClientPolicy**與**授與 CSClientPolicy** 。

</div>

<span> </span>

</div>

</div>

</div>

