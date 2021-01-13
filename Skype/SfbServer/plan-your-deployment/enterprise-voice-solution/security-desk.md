---
title: 在商務用 Skype 中包含安全性桌面伺服器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: 規劃如何在 E9-1-1 部署中將組織的安全性服務台納入商務用 Skype Server Enterprise Voice。
ms.openlocfilehash: 756af940eb327bc4744454e9ed9ef7a7fbfd517d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813403"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a><span data-ttu-id="34299-103">在商務用 Skype 中包含安全性桌面伺服器</span><span class="sxs-lookup"><span data-stu-id="34299-103">Include the security desk in Skype for Business Server</span></span>
 
<span data-ttu-id="34299-104">規劃如何在 E9-1-1 部署中將組織的安全性服務台納入商務用 Skype Server Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="34299-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="34299-p101">您的公司可能需要警衛室介入處理緊急通話。為了協助決定如何將警衛室整合至 E9-1-1 部署，您應該回答下列問題。</span><span class="sxs-lookup"><span data-stu-id="34299-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="34299-107">**您是否希望在有人撥打緊急通話時通知警衛室？**</span><span class="sxs-lookup"><span data-stu-id="34299-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="34299-108">您可以設定位置原則，讓商務用 Skype 伺服器將立即訊息 (IM) 警示傳送至一或多個安全性人員的商務用 Skype SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="34299-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="34299-109">這些通知包含撥打緊急電話的人員名稱、號碼及位置，以加速安全人員協助處理緊急狀況。</span><span class="sxs-lookup"><span data-stu-id="34299-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="34299-110">**您想要針對每一通緊急通話都邀請警衛室參加會議嗎？**</span><span class="sxs-lookup"><span data-stu-id="34299-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="34299-p103">只要緊急服務服務提供者有支援，您可以設定位置原則，以隨每通緊急通話附上回撥號碼。然後提供者就會針對緊急電話，使用此號碼來召集您組織的安全人員開會。此會議可在位置原則中設定為單向 (只能聆聽) 或雙向。</span><span class="sxs-lookup"><span data-stu-id="34299-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="34299-p104">必要時，您可以為每個位置原則設定不同的緊急人員。這樣可讓您針對公司內的不同區域自訂回應，或針對來自網路內部和外部的緊急電話分別建立不同的行為。您可以使用通訊群組來指定想要通知的人員。</span><span class="sxs-lookup"><span data-stu-id="34299-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

