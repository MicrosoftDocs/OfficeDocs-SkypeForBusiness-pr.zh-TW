---
title: 在商務用 Skype Server 中加入安全服務台
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: 在商務用 Skype Server Enterprise Voice 中, 規劃如何將貴組織的安全服務台納入 E9 部署。
ms.openlocfilehash: 7be3533879f36c897d148194345e1496945359b6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187561"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a><span data-ttu-id="0ac2a-103">在商務用 Skype Server 中加入安全服務台</span><span class="sxs-lookup"><span data-stu-id="0ac2a-103">Include the security desk in Skype for Business Server</span></span>
 
<span data-ttu-id="0ac2a-104">在商務用 Skype Server Enterprise Voice 中, 規劃如何將貴組織的安全服務台納入 E9 部署。</span><span class="sxs-lookup"><span data-stu-id="0ac2a-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="0ac2a-105">您的公司可能需要安全服務台才能參與緊急通話。</span><span class="sxs-lookup"><span data-stu-id="0ac2a-105">Your company may require the security desk to become involved in an emergency call.</span></span> <span data-ttu-id="0ac2a-106">若要協助您決定如何將安全服務台整合至 E9-1 1 1, 您應該回答下列問題。</span><span class="sxs-lookup"><span data-stu-id="0ac2a-106">To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="0ac2a-107">**您希望安全服務台在有緊急通話時收到通知嗎？**</span><span class="sxs-lookup"><span data-stu-id="0ac2a-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="0ac2a-108">您可以設定位置原則, 讓商務用 Skype 伺服器傳送立即訊息 (IM) 通知給一或多個安全性人員的商務用 Skype SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="0ac2a-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="0ac2a-109">這些警示包含撥入緊急通話之人員的名稱、電話號碼和地點, 以及協助安全人員協助緊急情況。</span><span class="sxs-lookup"><span data-stu-id="0ac2a-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="0ac2a-110">**您是否想要在每次緊急通話中舉行安全服務台？**</span><span class="sxs-lookup"><span data-stu-id="0ac2a-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="0ac2a-111">如果緊急服務服務提供者支援, 您可以設定位置原則, 在每次緊急通話中加入回撥號碼。</span><span class="sxs-lookup"><span data-stu-id="0ac2a-111">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call.</span></span> <span data-ttu-id="0ac2a-112">然後, 提供者會使用這個數位, 將貴組織的安全性人員加入緊急通話中。</span><span class="sxs-lookup"><span data-stu-id="0ac2a-112">This number is then used by the provider to conference your organization's security personnel into emergency calls.</span></span> <span data-ttu-id="0ac2a-113">此會議可在位置原則中設定為單向 (僅供聆聽) 或雙向 (雙向)。</span><span class="sxs-lookup"><span data-stu-id="0ac2a-113">This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="0ac2a-114">如有需要, 您可以針對每個位置原則設定不同的緊急人員。</span><span class="sxs-lookup"><span data-stu-id="0ac2a-114">If desired, you can configure different emergency personnel for each location policy.</span></span> <span data-ttu-id="0ac2a-115">這可讓您自訂公司內部不同區域的回應, 或針對來源於網路以外的緊急呼叫建立不同的行為。</span><span class="sxs-lookup"><span data-stu-id="0ac2a-115">This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network.</span></span> <span data-ttu-id="0ac2a-116">您可以使用通訊群組來指定您想要通知的人員。</span><span class="sxs-lookup"><span data-stu-id="0ac2a-116">You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

