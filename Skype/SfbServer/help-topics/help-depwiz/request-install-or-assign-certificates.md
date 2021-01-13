---
title: 要求、安裝或指派憑證
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
description: '[步驟 3：要求、安裝或指派憑證] 會在您按一下 [執行] 時啟動 [憑證精靈]。 透過嚮導所設定的憑證是以商務用 Skype Server 2015 拓撲的定義為基礎，而拓撲產生器是由拓撲產生器所設定併發布到中央管理存放區。 為了順利對組織中的線上憑證授權單位 (CA) 執行 [憑證精靈]，您必須以電腦本機系統管理員群組的成員身分登入電腦。 在電腦和 CA 所在的網域中，您也必須是經過驗證的網域使用者。 憑證嚮導可讓您指定用來存取組織之 CA 的替代認證。'
ms.openlocfilehash: 278aea23430d2fad39c355f03c7512a76ab9cbee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829713"
---
# <a name="request-install-or-assign-certificates"></a><span data-ttu-id="dc13c-107">要求、安裝或指派憑證</span><span class="sxs-lookup"><span data-stu-id="dc13c-107">Request, Install, or Assign Certificates</span></span>
 
 <span data-ttu-id="dc13c-108">**[步驟 3：要求、安裝或指派憑證]** 會在您按一下 **[執行]** 時啟動 [憑證精靈]。</span><span class="sxs-lookup"><span data-stu-id="dc13c-108">**Step 3: Request, Install or Assign Certificates** starts the Certificate Wizard when you click **Run**.</span></span> <span data-ttu-id="dc13c-109">透過嚮導所設定的憑證是以商務用 Skype Server 2015 拓撲的定義為基礎，而拓撲產生器是由拓撲產生器所設定併發布到中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="dc13c-109">The certificates that are configured through the wizard are based on the definition of the Skype for Business Server 2015 topology that is configured and published by Topology Builder to the Central Management store.</span></span> <span data-ttu-id="dc13c-110">為了順利對組織中的線上憑證授權單位 (CA) 執行 [憑證精靈]，您必須以電腦本機系統管理員群組的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="dc13c-110">To successfully run the Certificate Wizard for an online certification authority (CA) in your organization, you must be logged on to the computer as a user who is a member of the computer local administrators group.</span></span> <span data-ttu-id="dc13c-111">在電腦和 CA 所在的網域中，您也必須是經過驗證的網域使用者。</span><span class="sxs-lookup"><span data-stu-id="dc13c-111">You must also be an authenticated Domain User in the domain where the computer and the CA exist.</span></span> <span data-ttu-id="dc13c-112">憑證嚮導可讓您指定用來存取組織之 CA 的替代認證。</span><span class="sxs-lookup"><span data-stu-id="dc13c-112">The certificate wizard does provide the ability to specify alternate credentials for access your organization's CA.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc13c-p103">您也可以使用 [憑證精靈]，要求及處理傳送至公用 CA 或其他離線公開金鑰基礎結構 (PKI) 的離線憑證要求。若要產生離線要求，除了登入電腦所需的群組成員資格外，不需要其他特定群組成員資格。若要處理公用 CA 回應及指派憑證給電腦和角色，您必須以本機 Administrators 群組成員或相等的身分登入。</span><span class="sxs-lookup"><span data-stu-id="dc13c-p103">You can also use the Certificate Wizard to request and process offline certificate requests that are sent to a public CA or other offline public key infrastructure (PKI). There are no specific group memberships, other than those needed to log on to the computer, to generate an offline request. To process the public CA response and to assign the certificate to the computer and role, you must be logged on as a member of the local Administrators group or equivalent.</span></span> 
  

