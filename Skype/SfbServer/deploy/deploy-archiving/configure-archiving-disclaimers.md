---
title: 針對商務用 Skype Server 中的外部使用者設定封存免責聲明
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 摘要：請閱讀本主題，以瞭解如何針對商務用 Skype Server 設定封存免責聲明。
ms.openlocfilehash: d6c08b6fe2eaa6c74231b96346661488c3f8e2b0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001053"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a><span data-ttu-id="ea8db-103">針對商務用 Skype Server 中的外部使用者設定封存免責聲明</span><span class="sxs-lookup"><span data-stu-id="ea8db-103">Configure archiving disclaimers for external users in Skype for Business Server</span></span>
 
<span data-ttu-id="ea8db-104">**摘要：** 若要瞭解如何針對商務用 Skype Server 設定封存免責聲明，請閱讀本主題。</span><span class="sxs-lookup"><span data-stu-id="ea8db-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server.</span></span>
  
<span data-ttu-id="ea8db-105">如果您的組織與外部合作夥伴溝通，您必須讓他們知道您正在與他們封存通訊。</span><span class="sxs-lookup"><span data-stu-id="ea8db-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="ea8db-106">當您部署邊緣伺服器並為貴組織啟用同盟時，系統會詢問您是否要將封存免責聲明自動傳送給外部合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="ea8db-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="ea8db-107">如果您需要變更此設定，您可以使用商務用 Skype Server 的 [控制台] 或 [Windows PowerShell **CsAccessEdgeConfiguration** ] Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ea8db-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="ea8db-108">您可以從商務用 Skype Server management 命令介面或從 Windows PowerShell 遠端會話執行 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ea8db-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="ea8db-109">若要讓外部使用者在商務用 Skype Server 部署中與使用者共同作業，您也必須至少設定一個外部存取原則以支援外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="ea8db-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="ea8db-110">如需詳細資訊，請參閱管理貴組織的 XMPP 聯盟合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="ea8db-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="ea8db-111">如需控制特定聯盟網域存取權的詳細資料，請參閱依個別聯盟網域控制存取權。</span><span class="sxs-lookup"><span data-stu-id="ea8db-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="ea8db-112">使用 [控制台] 啟用或停用封存放棄免責聲明</span><span class="sxs-lookup"><span data-stu-id="ea8db-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="ea8db-113">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="ea8db-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ea8db-114">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="ea8db-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="ea8db-115">在左側導覽列中，按一下 [**同盟與外部存取**]，然後按一下 [**存取邊緣**設定]。</span><span class="sxs-lookup"><span data-stu-id="ea8db-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="ea8db-116">按一下 [**存取邊緣**設定] 索引標籤上的 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="ea8db-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="ea8db-117">在 [**編輯存取邊緣**設定] 的 [**啟用同盟及公用 IM**連線] 底下，選取或清除 [**將封存放棄免責聲明傳送給聯盟夥伴**] 核取方塊，以啟用或停用自動傳送封存免責聲明。</span><span class="sxs-lookup"><span data-stu-id="ea8db-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="ea8db-118">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ea8db-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="ea8db-119">使用 Windows PowerShell 啟用或停用封存放棄免責聲明</span><span class="sxs-lookup"><span data-stu-id="ea8db-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="ea8db-120">若要啟用封存免責聲明，請將**EnableArchivingDisclaimer**屬性的值設定為 True （$True）：</span><span class="sxs-lookup"><span data-stu-id="ea8db-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="ea8db-121">若要停用封存免責聲明，請將**EnableArchivingDisclaimer**屬性的值設定為 False （$False）：</span><span class="sxs-lookup"><span data-stu-id="ea8db-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


