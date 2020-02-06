---
title: 在商務用 Skype Server 中部署視頻交互操作伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 摘要：在商務用 Skype Server 中部署 VIS 伺服器角色。
ms.openlocfilehash: 51db16a115871f7720379157aa1b97ae89e9031f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798030"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="df915-103">在商務用 Skype Server 中部署視頻交互操作伺服器</span><span class="sxs-lookup"><span data-stu-id="df915-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="df915-104">**摘要：** 在商務用 Skype Server 中部署 VIS 伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="df915-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="df915-105">商務用 Skype Server 現在可以直接與 Cisco teleconferencing 系統（VTCs）整合（例如 Cisco C60 或 Cisco MX300）。</span><span class="sxs-lookup"><span data-stu-id="df915-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="df915-106">這需要引入一個名為「視頻交互操作伺服器」（VIS）的新伺服器角色，並正確設定其將與之互動的 VIS 和裝置。</span><span class="sxs-lookup"><span data-stu-id="df915-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="df915-107">現有 Cisco 基礎結構的 VTC 寄存器（例如 Cisco 整合通訊管理員（CUCM）），以及 CUCM 與 VIS 池中使用的視頻 SIP 幹線。</span><span class="sxs-lookup"><span data-stu-id="df915-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="df915-108">本節內容</span><span class="sxs-lookup"><span data-stu-id="df915-108">In this section</span></span>

<span data-ttu-id="df915-109">在 VIS 伺服器或池與 VTC 系統之間設定互通性，需要執行下列五個程式：</span><span class="sxs-lookup"><span data-stu-id="df915-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="df915-110">在商務用 Skype Server 中建立 VIS 池</span><span class="sxs-lookup"><span data-stu-id="df915-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="df915-111">在商務用 Skype Server 中部署 VIS 伺服器角色</span><span class="sxs-lookup"><span data-stu-id="df915-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="df915-112">在商務用 Skype Server 中設定視頻交互操作伺服器</span><span class="sxs-lookup"><span data-stu-id="df915-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="df915-113">設定 CUCM 以與商務用 Skype 伺服器進行交互操作</span><span class="sxs-lookup"><span data-stu-id="df915-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="df915-114">設定與商務用 Skype 伺服器交互操作的 VTC</span><span class="sxs-lookup"><span data-stu-id="df915-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="df915-115">相關章節</span><span class="sxs-lookup"><span data-stu-id="df915-115">Related sections</span></span>

[<span data-ttu-id="df915-116">在商務用 Skype Server 中規劃影片互通性伺服器</span><span class="sxs-lookup"><span data-stu-id="df915-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

