---
title: Lync Server 2013：新增自訂文字到立即訊息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b54b4724568a4f57bebc7ef6162a553cfdd9a091
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a><span data-ttu-id="45d43-102">在 Lync Server 2013 中新增自訂文字到立即訊息</span><span class="sxs-lookup"><span data-stu-id="45d43-102">Adding custom text to instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45d43-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="45d43-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="45d43-104">在每個 Lync 2013 立即訊息（IM）交談的開頭，使用**新的 CSClientPolicy**或 CSClientPolicy 的 Lync Server Management Shell Cmdlet （含 IMWarning 參數 **）** ，將免責聲明或警告新增到其中。</span><span class="sxs-lookup"><span data-stu-id="45d43-104">Add a disclaimer or warning to the beginning of every Lync 2013 instant messaging (IM) conversation by using the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the IMWarning parameter.</span></span>

<span data-ttu-id="45d43-105">下列範例中的命令會在您每次開始新的 IM 交談時，在 [交談] 視窗的頂端新增安全性提醒：</span><span class="sxs-lookup"><span data-stu-id="45d43-105">The command in the following example adds a security reminder at the top of the Conversation window whenever a new IM conversation begins:</span></span>

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

<span data-ttu-id="45d43-106">使用**授與 CSClientPolicy**將此新原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="45d43-106">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="45d43-107">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的**新 CSClientPolicy**與**授與 CSClientPolicy** 。</span><span class="sxs-lookup"><span data-stu-id="45d43-107">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

