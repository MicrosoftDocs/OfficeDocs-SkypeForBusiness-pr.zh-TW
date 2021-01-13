---
title: 在商務用 Skype Server 2015 中安裝持續聊天元件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: 摘要：閱讀此主題以瞭解如何使用商務用 Skype Server 部署嚮導，以安裝商務用 Skype Server 2015 元件和服務。
ms.openlocfilehash: c3e68d5b5a41d06544f030df6877828da4b87c9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802083"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="5c082-103">在商務用 Skype Server 2015 中安裝持續聊天元件</span><span class="sxs-lookup"><span data-stu-id="5c082-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5c082-104">**摘要：** 閱讀此主題以瞭解如何使用商務用 Skype Server 部署嚮導，以安裝商務用 Skype Server 2015 元件和服務。</span><span class="sxs-lookup"><span data-stu-id="5c082-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="5c082-105">安裝 Persistent Chat 元件之前，請確定您已安裝必要的硬體和軟體，並已建立適當的拓撲來支援 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="5c082-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="5c082-106">如需規劃及需求的詳細資訊，請參閱商務用 [skype 環境的需求](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) ，以及 [在商務用 skype Server 2015 中規劃 Persistent Chat Server](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="5c082-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="5c082-107">如需如何更新及發行拓撲以包含 Persistent Chat Server 的詳細資訊，請參閱 [Add Persistent Chat server to To Business server 2015 拓撲](add-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="5c082-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="5c082-108">商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="5c082-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="5c082-109">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="5c082-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="5c082-110">如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="5c082-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="5c082-111">如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="5c082-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="5c082-112">安裝及啟動服務</span><span class="sxs-lookup"><span data-stu-id="5c082-112">Install and start services</span></span>

<span data-ttu-id="5c082-113">使用商務用 Skype 伺服器部署嚮導，選擇 [安裝或更新商務用 Skype 伺服器系統] 以執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="5c082-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="5c082-114">安裝本機組態存放區</span><span class="sxs-lookup"><span data-stu-id="5c082-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="5c082-115">安裝或移除商務用 Skype Server 元件</span><span class="sxs-lookup"><span data-stu-id="5c082-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="5c082-116">要求、安裝或指派憑證</span><span class="sxs-lookup"><span data-stu-id="5c082-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="5c082-117">啟動服務</span><span class="sxs-lookup"><span data-stu-id="5c082-117">Start services</span></span>
    
<span data-ttu-id="5c082-118">如需如何使用部署嚮導來安裝元件、指派憑證及啟動服務的詳細資訊，請參閱在拓撲中的伺服器上 [安裝商務用 Skype server 2015](../../deploy/install/install.md) 和 [安裝商務用 skype server 2015](../../deploy/install/install-skype-for-business-server.md)。</span><span class="sxs-lookup"><span data-stu-id="5c082-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

