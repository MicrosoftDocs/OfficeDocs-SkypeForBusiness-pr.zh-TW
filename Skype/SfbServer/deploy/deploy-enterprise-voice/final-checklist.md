---
title: 呼叫許可控制部署商務用 Skype Server 的最終檢查清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: 在商務用 Skype Server Enterprise Voice 中部署通話許可控制 (CAC) 的最終檢查清單。
ms.openlocfilehash: fab6472d931d0475a3e3b0a0f413fce7775d7a15
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189328"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a><span data-ttu-id="2721c-103">呼叫許可控制部署: 適用于商務用 Skype Server 的最終檢查清單</span><span class="sxs-lookup"><span data-stu-id="2721c-103">Call admission control deployment: final checklist for Skype for Business Server</span></span>
 
<span data-ttu-id="2721c-104">在商務用 Skype Server Enterprise Voice 中部署通話許可控制 (CAC) 的最終檢查清單。</span><span class="sxs-lookup"><span data-stu-id="2721c-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="2721c-105">使用下列檢查清單來確認您已完成所有必要的設定工作, 以部署呼叫許可控制 (CAC)。</span><span class="sxs-lookup"><span data-stu-id="2721c-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="2721c-106">如果一或多個邊緣伺服器已部署, 則必須將每個外部介面 IP 位址新增到 [網路設定] 中的子網清單中, 位元遮罩為32。</span><span class="sxs-lookup"><span data-stu-id="2721c-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="2721c-107">您也應該將這個子網 (IP 位址) 與「A/V Edge」服務所部署之地理位置的 [網路 site ID] 建立關聯。</span><span class="sxs-lookup"><span data-stu-id="2721c-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2721c-108">Edge 伺服器不是實現 CAC 所必需的。</span><span class="sxs-lookup"><span data-stu-id="2721c-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="2721c-109">請確定您已啟用 CAC, 如在[商務用 Skype Server 的 [啟用呼叫許可控制](enable-call-admission-control.md)] 中所述。</span><span class="sxs-lookup"><span data-stu-id="2721c-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="2721c-110">確定所有中央網站都已啟用 CAC。</span><span class="sxs-lookup"><span data-stu-id="2721c-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="2721c-111">這可以透過拓撲產生器完成。</span><span class="sxs-lookup"><span data-stu-id="2721c-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="2721c-112">如果您發佈時產生警告,*請勿*忽略。</span><span class="sxs-lookup"><span data-stu-id="2721c-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="2721c-113">確認在商業網路中管理的所有子網都已設定在 [網路設定] 中。</span><span class="sxs-lookup"><span data-stu-id="2721c-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="2721c-114">在[商務用 Skype 中部署網路區域、網站和子網](deploy-network.md)中所述, 您也必須將每個子網與網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="2721c-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
- <span data-ttu-id="2721c-115">確定所有前端伺服器、Survivable 分支裝置 (SBAs)、音訊/視訊會議伺服器 (如果在個別的池中), 以及在 [網路設定] 設定中設定了轉送伺服器的子網或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="2721c-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

