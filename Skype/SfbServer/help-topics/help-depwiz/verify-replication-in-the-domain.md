---
title: 驗證網域中的複寫
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
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: 若要驗證在步驟1： Prepare 架構中完成的網域準備作業，必須從商務用 Skype Server 管理命令介面 Lync Server 管理命令介面執行 Cmdlet。 若要執行 Windows PowerShell Cmdlet，請登入您準備好之網域成員的電腦，並以 Domain Admins 群組成員的身分登入。 執行下列動作：
ms.openlocfilehash: d002a0623d6788183a5b09f8e58262fc1c68a823
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800593"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="3d312-105">驗證網域中的複寫</span><span class="sxs-lookup"><span data-stu-id="3d312-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="3d312-106">若要驗證在 **步驟1： Prepare 架構** 中完成的網域準備作業，必須從商務用 Skype Server 管理命令介面 Lync Server 管理命令介面執行 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3d312-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="3d312-107">若要執行 Windows PowerShell Cmdlet，請登入您準備好之網域成員的電腦，並以 Domain Admins 群組成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="3d312-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="3d312-108">執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3d312-108">Do the following:</span></span>
  
1. <span data-ttu-id="3d312-109">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="3d312-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="3d312-110">在 [Windows PowerShell] 中，輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="3d312-110">In Windows PowerShell, type the following:</span></span>
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="3d312-111">例如：</span><span class="sxs-lookup"><span data-stu-id="3d312-111">For example:</span></span>
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="3d312-112">GlobalSettingsDomainController 參數可讓您指出全域設定的存放位置。</span><span class="sxs-lookup"><span data-stu-id="3d312-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="3d312-113">如果您的設定儲存在系統容器中 (（一般情況下，升級部署尚未將全域設定遷移至設定容器) ），您可以在 Active Directory 網域服務樹系的根目錄中定義網域控制站。</span><span class="sxs-lookup"><span data-stu-id="3d312-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="3d312-114">如果全域設定位於 Configuration 容器中 (在全新部署或升級部署作業期間，當設定已經移轉至 Configuration 容器時的常見現象)，您可以在樹系中定義任何網域控制站。</span><span class="sxs-lookup"><span data-stu-id="3d312-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="3d312-115">如果您未指定此參數，Cmdlet 會假設設定儲存在設定容器中，並參照至 Active Directory 中的任何網域控制站。</span><span class="sxs-lookup"><span data-stu-id="3d312-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="3d312-116">如果您沒有指定 Domain 參數，這個值會設為本機網域。</span><span class="sxs-lookup"><span data-stu-id="3d312-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="3d312-117">這個 Cmdlet 會在網域準備工作順利完成時，傳回值 **LC_DOMAIN_SETTINGS_STATE_READY**。</span><span class="sxs-lookup"><span data-stu-id="3d312-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

