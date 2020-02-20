---
title: Lync Server 2013： 包括安全性桌面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Including the security desk
ms:assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398299(v=OCS.15)
ms:contentKeyID: 48184084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 114efc7af1b4b566aa7af6ea558961966dd0c60b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="including-the-security-desk-in-lync-server-2013"></a><span data-ttu-id="bb52b-102">Lync Server 2013 中包括安全性桌面</span><span class="sxs-lookup"><span data-stu-id="bb52b-102">Including the security desk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb52b-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="bb52b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="bb52b-p101">您的公司可能需要警衛室介入處理緊急通話。為了協助決定如何將警衛室整合至 E9-1-1 部署，您應該回答下列問題。</span><span class="sxs-lookup"><span data-stu-id="bb52b-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>

  - <span data-ttu-id="bb52b-106">**您是否希望在有人撥打緊急通話時通知警衛室？**</span><span class="sxs-lookup"><span data-stu-id="bb52b-106">**Do you want the security desk to be notified when there is an emergency call?**</span></span>  
    <span data-ttu-id="bb52b-107">您可以設定的位置原則，讓該 Lync Server 傳送立即訊息 (IM) 提醒一或多個安全性人員的 Lync SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="bb52b-107">You can configure the location policy so that Lync Server sends instant messaging (IM) alerts to the Lync SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="bb52b-108">這些通知包含撥打緊急電話的人員名稱、號碼及位置，以加速安全人員協助處理緊急狀況。</span><span class="sxs-lookup"><span data-stu-id="bb52b-108">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>

<!-- end list -->

  - <span data-ttu-id="bb52b-109">**您想要針對每一通緊急通話都邀請警衛室參加會議嗎？**</span><span class="sxs-lookup"><span data-stu-id="bb52b-109">**Do you want to conference the security desk in on each emergency call?**</span></span>  
    <span data-ttu-id="bb52b-p103">只要緊急服務服務提供者有支援，您可以設定位置原則，以隨每通緊急通話附上回撥號碼。然後提供者就會針對緊急電話，使用此號碼來召集您組織的安全人員開會。此會議可在位置原則中設定為單向 (只能聆聽) 或雙向。</span><span class="sxs-lookup"><span data-stu-id="bb52b-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bb52b-p104">必要時，您可以為每個位置原則設定不同的緊急人員。這樣可讓您針對公司內的不同區域自訂回應，或針對來自網路內部和外部的緊急電話分別建立不同的行為。您可以使用通訊群組來指定想要通知的人員。</span><span class="sxs-lookup"><span data-stu-id="bb52b-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

