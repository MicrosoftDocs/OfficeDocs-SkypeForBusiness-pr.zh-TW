---
title: 驗證網域中的複寫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 若要驗證在步驟1：準備架構中完成的網域準備，必須從商務用 Skype Server Management Shell Lync Server 管理命令介面執行 Cmdlet。 若要執行 Windows PowerShell Cmdlet，請登入您已準備之網域成員的電腦，以及作為網域管理員群組的成員。 請執行下列步驟：
ms.openlocfilehash: c378aabe27ce69351643455c41acfd35a8e950b6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992148"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="1793b-105">驗證網域中的複寫</span><span class="sxs-lookup"><span data-stu-id="1793b-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="1793b-106">若要驗證在**步驟1：準備架構**中完成的網域準備，必須從商務用 Skype Server Management Shell Lync Server 管理命令介面執行 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1793b-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="1793b-107">若要執行 Windows PowerShell Cmdlet，請登入您已準備之網域成員的電腦，以及作為網域管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1793b-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="1793b-108">請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1793b-108">Do the following:</span></span>
  
1. <span data-ttu-id="1793b-109">啟動商務用 Skype Server 管理命令介面：請依序按一下 [**開始**]、[**所有程式**]、[**商務用 skype**]，然後按一下 [**商務用 skype server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="1793b-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1793b-110">在 Windows PowerShell 中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="1793b-110">In Windows PowerShell, type the following:</span></span>
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="1793b-111">例如：</span><span class="sxs-lookup"><span data-stu-id="1793b-111">For example:</span></span>
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="1793b-112">GlobalSettingsDomainController 參數可讓您指出全域設定的存放位置。</span><span class="sxs-lookup"><span data-stu-id="1793b-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="1793b-113">如果您的設定是儲存在系統容器中（這通常是使用未將全域設定遷移至配置容器的升級部署），您可以在 Active Directory 網域服務林的根目錄中定義網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="1793b-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="1793b-114">如果全域設定位於 Configuration 容器中 (在全新部署或升級部署作業期間，當設定已經移轉至 Configuration 容器時的常見現象)，您可以在樹系中定義任何網域控制站。</span><span class="sxs-lookup"><span data-stu-id="1793b-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="1793b-115">如果您沒有指定此參數，Cmdlet 會假設設定會儲存在配置容器中，並參照 Active Directory 中的任何網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="1793b-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="1793b-116">如果您沒有指定 Domain 參數，則會將此值設定至本機網域。</span><span class="sxs-lookup"><span data-stu-id="1793b-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="1793b-117">這個 Cmdlet 會在網域準備工作完成時，傳回 **LC_DOMAIN_SETTINGS_STATE_READY** 值。</span><span class="sxs-lookup"><span data-stu-id="1793b-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

