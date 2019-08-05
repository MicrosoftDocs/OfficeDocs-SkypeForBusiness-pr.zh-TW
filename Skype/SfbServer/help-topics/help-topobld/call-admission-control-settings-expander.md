---
title: 通話許可控制設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: 通話許可控制 (CAC) 是由地區、網站和子網路所構成的網路，可讓您根據可用頻寬來限制音訊和視訊傳輸。在設定 CAC 的網路之後，您必須啟用 CAS，才能強制執行頻寬限制。
ms.openlocfilehash: 7f5da16b1f3854f676f550c4f2484e950adf86fb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193776"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="80515-104">通話許可控制設定展開工具</span><span class="sxs-lookup"><span data-stu-id="80515-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="80515-p102">通話許可控制 (CAC) 是由地區、網站和子網路所構成的網路，可讓您根據可用頻寬來限制音訊和視訊傳輸。在設定 CAC 的網路之後，您必須啟用 CAS，才能強制執行頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="80515-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="80515-107">您也可以使用控制台或管理命令介面 Cmdlet 來啟用 CAC。</span><span class="sxs-lookup"><span data-stu-id="80515-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="80515-108">在網站的 [編輯內容]\*\*\*\* 對話方塊的 [通話許可控制設定]\*\*\*\* 區段中，您可以變更下列設定：</span><span class="sxs-lookup"><span data-stu-id="80515-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="80515-109">**啟用呼叫許可控制**選取此設定以啟用 CAC。</span><span class="sxs-lookup"><span data-stu-id="80515-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="80515-110">清除此設定以針對您的整個網路停用 CAC。</span><span class="sxs-lookup"><span data-stu-id="80515-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="80515-111">若要啟用 CAC, 您必須將您的網路設定為 CAC。</span><span class="sxs-lookup"><span data-stu-id="80515-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="80515-112">如需詳細資訊, 請參閱部署檔中的[商務用 Skype Server 2015 中的 [部署呼叫許可控制](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md)]。</span><span class="sxs-lookup"><span data-stu-id="80515-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="80515-113">**用於執行呼叫許可控制的 [前端] 池**如果您啟用的是 CAC, 您可以變更執行它的池。</span><span class="sxs-lookup"><span data-stu-id="80515-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="80515-114">從下拉式清單中選取 [[] 池。</span><span class="sxs-lookup"><span data-stu-id="80515-114">Select the pool from the drop-down list.</span></span>
    

