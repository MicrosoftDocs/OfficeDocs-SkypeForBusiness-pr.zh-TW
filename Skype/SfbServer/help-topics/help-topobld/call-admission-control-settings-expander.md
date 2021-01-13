---
title: 通話許可控制服務設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: 通話許可控制 (CAC) 是由地區、網站和子網路所構成的網路，可讓您根據可用頻寬來限制音訊和視訊傳輸。在設定 CAC 的網路之後，您必須啟用 CAS，才能強制執行頻寬限制。
ms.openlocfilehash: 1278cb19e4c8df047d97e5f391ca940255f094cc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833113"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="a32c4-104">通話許可控制服務設定展開工具</span><span class="sxs-lookup"><span data-stu-id="a32c4-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="a32c4-p102">通話許可控制 (CAC) 是由地區、網站和子網路所構成的網路，可讓您根據可用頻寬來限制音訊和視訊傳輸。在設定 CAC 的網路之後，您必須啟用 CAS，才能強制執行頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="a32c4-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a32c4-107">您也可以使用控制台或管理命令介面 Cmdlet 來啟用 CAC。</span><span class="sxs-lookup"><span data-stu-id="a32c4-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="a32c4-108">在網站的 **[編輯內容]** 對話方塊的 **[通話許可控制設定]** 區段中，您可以變更下列設定：</span><span class="sxs-lookup"><span data-stu-id="a32c4-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="a32c4-109">**啟用通話許可控制** 選取此設定以啟用 CAC。</span><span class="sxs-lookup"><span data-stu-id="a32c4-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="a32c4-110">清除此設定，以停用整個網路的 CAC。</span><span class="sxs-lookup"><span data-stu-id="a32c4-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="a32c4-111">若要啟用 CAC，您必須將您的網路設定為 CAC。</span><span class="sxs-lookup"><span data-stu-id="a32c4-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="a32c4-112">如需詳細資訊，請參閱部署檔中的 [在商務用 Skype Server 2015 中部署通話許可控制](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 。</span><span class="sxs-lookup"><span data-stu-id="a32c4-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="a32c4-113">**執行通話許可控制的前端集** 區如果您啟用 CAC，您可以變更執行它的集區。</span><span class="sxs-lookup"><span data-stu-id="a32c4-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="a32c4-114">從下拉式清單中選取集區。</span><span class="sxs-lookup"><span data-stu-id="a32c4-114">Select the pool from the drop-down list.</span></span>
    

