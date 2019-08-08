---
title: 安裝常設聊天室元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: '摘要: 請閱讀本主題, 瞭解如何使用商務用 Skype Server 部署嚮導來安裝商務用 Skype Server 2015 元件及服務。'
ms.openlocfilehash: 5b8205cb2ab828001eae76eeaab8cd4f697c9315
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234738"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="fef7c-103">安裝常設聊天室元件</span><span class="sxs-lookup"><span data-stu-id="fef7c-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fef7c-104">**摘要:** 請閱讀本主題, 瞭解如何使用商務用 Skype Server 部署嚮導來安裝商務用 Skype Server 2015 元件及服務。</span><span class="sxs-lookup"><span data-stu-id="fef7c-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="fef7c-105">在安裝持續聊天元件之前, 請確定您已安裝必要的硬體和軟體, 並已建立適當的拓撲來支援永久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="fef7c-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="fef7c-106">如需規劃與需求的詳細資訊, 請參閱[商務用 skype 環境的需求](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md), 以及[在商務用 skype Server 2015 中規劃持續聊天伺服器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="fef7c-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="fef7c-107">如需如何更新及發佈拓撲以包含持續聊天伺服器的相關資訊, 請參閱[在商務用 Skype server 2015 拓撲中新增永久聊天伺服器](add-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="fef7c-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="fef7c-108">商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="fef7c-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="fef7c-109">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="fef7c-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="fef7c-110">如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="fef7c-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="fef7c-111">如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="fef7c-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="fef7c-112">安裝並啟動服務</span><span class="sxs-lookup"><span data-stu-id="fef7c-112">Install and start services</span></span>

<span data-ttu-id="fef7c-113">使用商務用 Skype Server 部署嚮導, 選擇 [安裝或更新商務用 Skype Server System], 以執行下列步驟:</span><span class="sxs-lookup"><span data-stu-id="fef7c-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="fef7c-114">安裝本機設定存放區</span><span class="sxs-lookup"><span data-stu-id="fef7c-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="fef7c-115">安裝或移除商務用 Skype Server 元件</span><span class="sxs-lookup"><span data-stu-id="fef7c-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="fef7c-116">要求、安裝或指派憑證</span><span class="sxs-lookup"><span data-stu-id="fef7c-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="fef7c-117">啟動服務</span><span class="sxs-lookup"><span data-stu-id="fef7c-117">Start services</span></span>
    
<span data-ttu-id="fef7c-118">如需如何使用 [部署嚮導] 來安裝元件、指派證書及啟動服務的詳細資料, 請參閱[在拓撲中的伺服器上](../../deploy/install/install-skype-for-business-server.md)[安裝商務用 skype Server 2015](../../deploy/install/install.md)並安裝商務用 skype server 2015。</span><span class="sxs-lookup"><span data-stu-id="fef7c-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

