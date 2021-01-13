---
title: 在商務用 Skype Server 中部署影片 Interop 伺服器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 7b3ee96b1ff2e6c633efa9e1cc98aa14bb5babc3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801953"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="19d92-103">在商務用 Skype Server 中部署影片 Interop 伺服器</span><span class="sxs-lookup"><span data-stu-id="19d92-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="19d92-104">**摘要：** 在商務用 Skype Server 中部署 VIS 伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="19d92-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="19d92-105">商務用 Skype 伺服器現在可以直接與 Cisco 電話會議系統整合 (VTCs) （如 Cisco C60 或 Cisco MX300）。</span><span class="sxs-lookup"><span data-stu-id="19d92-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="19d92-106">這需要引入新的伺服器角色，稱為「影片 Interop」伺服器 (VIS) ，並正確設定 VIS 和其會與其互動的裝置。</span><span class="sxs-lookup"><span data-stu-id="19d92-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="19d92-107">VTC 會使用現有的 Cisco 基礎結構（例如 Cisco 整合通訊管理員 (CUCM) ）登錄，並在 CUCM 與 VIS 集區之間使用視頻 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="19d92-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="19d92-108">本節內容</span><span class="sxs-lookup"><span data-stu-id="19d92-108">In this section</span></span>

<span data-ttu-id="19d92-109">設定 VIS server 或集區與 VTC 系統之間的互通性時，需要執行下列五個程式：</span><span class="sxs-lookup"><span data-stu-id="19d92-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="19d92-110">在商務用 Skype Server 中建立 VIS 集區</span><span class="sxs-lookup"><span data-stu-id="19d92-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="19d92-111">在商務用 Skype Server 中部署 VIS 伺服器角色</span><span class="sxs-lookup"><span data-stu-id="19d92-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="19d92-112">在商務用 Skype Server 中設定視頻 Interop 伺服器</span><span class="sxs-lookup"><span data-stu-id="19d92-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="19d92-113">設定 CUCM 以搭配商務用 Skype 伺服器進行交互操作</span><span class="sxs-lookup"><span data-stu-id="19d92-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="19d92-114">設定 VTC 以搭配商務用 Skype 伺服器進行交互操作</span><span class="sxs-lookup"><span data-stu-id="19d92-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="19d92-115">相關章節</span><span class="sxs-lookup"><span data-stu-id="19d92-115">Related sections</span></span>

[<span data-ttu-id="19d92-116">在商務用 Skype Server 中規劃影片 Interop 伺服器</span><span class="sxs-lookup"><span data-stu-id="19d92-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

