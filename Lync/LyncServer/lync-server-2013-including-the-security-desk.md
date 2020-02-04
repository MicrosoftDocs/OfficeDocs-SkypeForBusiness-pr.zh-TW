---
title: Lync Server 2013：包括安全服務台
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
ms.openlocfilehash: d792626a973a790313b2cdc1bd9df9092175f28a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="including-the-security-desk-in-lync-server-2013"></a><span data-ttu-id="35549-102">包括 Lync Server 2013 中的安全服務台</span><span class="sxs-lookup"><span data-stu-id="35549-102">Including the security desk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35549-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="35549-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="35549-104">您的公司可能需要安全服務台才能參與緊急通話。</span><span class="sxs-lookup"><span data-stu-id="35549-104">Your company may require the security desk to become involved in an emergency call.</span></span> <span data-ttu-id="35549-105">若要協助您決定如何將安全服務台整合至 E9-1 1 1，您應該回答下列問題。</span><span class="sxs-lookup"><span data-stu-id="35549-105">To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>

  - <span data-ttu-id="35549-106">**您希望安全服務台在有緊急通話時收到通知嗎？**</span><span class="sxs-lookup"><span data-stu-id="35549-106">**Do you want the security desk to be notified when there is an emergency call?**</span></span>  
    <span data-ttu-id="35549-107">您可以設定位置原則，讓 Lync Server 將立即訊息（IM）通知傳送給一或多個安全性人員的 Lync SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="35549-107">You can configure the location policy so that Lync Server sends instant messaging (IM) alerts to the Lync SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="35549-108">這些警示包含撥入緊急通話之人員的名稱、電話號碼和地點，以及協助安全人員協助緊急情況。</span><span class="sxs-lookup"><span data-stu-id="35549-108">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>

<!-- end list -->

  - <span data-ttu-id="35549-109">**您是否想要在每次緊急通話中舉行安全服務台？**</span><span class="sxs-lookup"><span data-stu-id="35549-109">**Do you want to conference the security desk in on each emergency call?**</span></span>  
    <span data-ttu-id="35549-110">如果緊急服務服務提供者支援，您可以設定位置原則，在每次緊急通話中加入回撥號碼。</span><span class="sxs-lookup"><span data-stu-id="35549-110">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call.</span></span> <span data-ttu-id="35549-111">然後，提供者會使用這個數位，將貴組織的安全性人員加入緊急通話中。</span><span class="sxs-lookup"><span data-stu-id="35549-111">This number is then used by the provider to conference your organization's security personnel into emergency calls.</span></span> <span data-ttu-id="35549-112">此會議可在位置原則中設定為單向（僅供聆聽）或雙向（雙向）。</span><span class="sxs-lookup"><span data-stu-id="35549-112">This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="35549-113">如有需要，您可以針對每個位置原則設定不同的緊急人員。</span><span class="sxs-lookup"><span data-stu-id="35549-113">If desired, you can configure different emergency personnel for each location policy.</span></span> <span data-ttu-id="35549-114">這可讓您自訂公司內部不同區域的回應，或針對來源於網路以外的緊急呼叫建立不同的行為。</span><span class="sxs-lookup"><span data-stu-id="35549-114">This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network.</span></span> <span data-ttu-id="35549-115">您可以使用通訊群組來指定您想要通知的人員。</span><span class="sxs-lookup"><span data-stu-id="35549-115">You can use distribution groups to specify the personnel you want to notify.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

