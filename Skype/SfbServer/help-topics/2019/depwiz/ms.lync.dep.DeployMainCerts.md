---
title: 要求、安裝或指派憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
ROBOTS: NOINDEX, NOFOLLOW
description: '[步驟 3：要求、安裝或指派憑證] 會在您按一下 [執行] 時啟動 [憑證精靈]。 透過嚮導所設定的憑證, 是以 [由拓撲 Builder] 設定併發布至 [中央管理] 儲存區的商務用 Skype 伺服器拓撲定義為基礎。 為了順利對組織中的線上憑證授權單位 (CA) 執行 [憑證精靈]，您必須以電腦本機系統管理員群組的成員身分登入電腦。 在電腦和 CA 所在的網域中，您也必須是經過驗證的網域使用者。 [憑證] 嚮導能提供指定備用認證以存取您組織的 CA 的功能。'
ms.openlocfilehash: faf6fa63770d27c90a94c01753d99a079cb5ef28
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193098"
---
# <a name="request-install-or-assign-certificates"></a><span data-ttu-id="6ed55-107">要求、安裝或指派憑證</span><span class="sxs-lookup"><span data-stu-id="6ed55-107">Request, Install, or Assign Certificates</span></span>
 
 <span data-ttu-id="6ed55-108">[步驟 3：要求、安裝或指派憑證] \*\*\*\* 會在您按一下 [執行] \*\*\*\* 時啟動 [憑證精靈]。</span><span class="sxs-lookup"><span data-stu-id="6ed55-108">**Step 3: Request, Install or Assign Certificates** starts the Certificate Wizard when you click **Run**.</span></span> <span data-ttu-id="6ed55-109">透過嚮導所設定的憑證, 是以 [由拓撲 Builder] 設定併發布至 [中央管理] 儲存區的商務用 Skype 伺服器拓撲定義為基礎。</span><span class="sxs-lookup"><span data-stu-id="6ed55-109">The certificates that are configured through the wizard are based on the definition of the Skype for Business Server topology that is configured and published by Topology Builder to the Central Management store.</span></span> <span data-ttu-id="6ed55-110">為了順利對組織中的線上憑證授權單位 (CA) 執行 [憑證精靈]，您必須以電腦本機系統管理員群組的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="6ed55-110">To successfully run the Certificate Wizard for an online certification authority (CA) in your organization, you must be logged on to the computer as a user who is a member of the computer local administrators group.</span></span> <span data-ttu-id="6ed55-111">在電腦和 CA 所在的網域中，您也必須是經過驗證的網域使用者。</span><span class="sxs-lookup"><span data-stu-id="6ed55-111">You must also be an authenticated Domain User in the domain where the computer and the CA exist.</span></span> <span data-ttu-id="6ed55-112">[憑證] 嚮導能提供指定備用認證以存取您組織的 CA 的功能。</span><span class="sxs-lookup"><span data-stu-id="6ed55-112">The certificate wizard does provide the ability to specify alternate credentials for access your organization's CA.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6ed55-p103">您也可以使用 [憑證精靈]，要求及處理傳送至公用 CA 或其他離線公開金鑰基礎結構 (PKI) 的離線憑證要求。若要產生離線要求，除了登入電腦所需的群組成員資格外，不需要其他特定群組成員資格。若要處理公用 CA 回應及指派憑證給電腦和角色，您必須以本機 Administrators 群組成員或相等的身分登入。</span><span class="sxs-lookup"><span data-stu-id="6ed55-p103">You can also use the Certificate Wizard to request and process offline certificate requests that are sent to a public CA or other offline public key infrastructure (PKI). There are no specific group memberships, other than those needed to log on to the computer, to generate an offline request. To process the public CA response and to assign the certificate to the computer and role, you must be logged on as a member of the local Administrators group or equivalent.</span></span> 
  

