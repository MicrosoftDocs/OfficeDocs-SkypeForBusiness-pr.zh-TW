---
title: 在商務用 Skype Server 中設定外部使用者的封存免責聲明
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
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 摘要：閱讀此主題以瞭解如何為商務用 Skype 伺服器設定封存免責聲明。
ms.openlocfilehash: 055c94f0fba18dcd9de35ff5a73e37de0b45595b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820663"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a><span data-ttu-id="cca63-103">在商務用 Skype Server 中設定外部使用者的封存免責聲明</span><span class="sxs-lookup"><span data-stu-id="cca63-103">Configure archiving disclaimers for external users in Skype for Business Server</span></span>
 
<span data-ttu-id="cca63-104">**摘要：** 閱讀此主題以瞭解如何為商務用 Skype 伺服器設定封存免責聲明。</span><span class="sxs-lookup"><span data-stu-id="cca63-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server.</span></span>
  
<span data-ttu-id="cca63-105">如果您的組織與外部合作夥伴進行通訊，您必須讓他們知道您正在封存與其通訊。</span><span class="sxs-lookup"><span data-stu-id="cca63-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="cca63-106">當您部署 Edge Server 並為您的組織啟用同盟時，系統會詢問您是否要自動將封存免責聲明傳送給外部合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="cca63-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="cca63-107">如果您需要變更此設定，您可以使用商務用 Skype Server 控制台或 Windows PowerShell **Set-CsAccessEdgeConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cca63-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="cca63-108">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cca63-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="cca63-109">若要讓外部使用者能夠與商務用 Skype Server 部署中的使用者共同作業，您也必須至少設定一個外部存取原則，以支援外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="cca63-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="cca63-110">如需詳細資訊，請參閱管理組織的 XMPP 同盟合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="cca63-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="cca63-111">如需控制特定同盟網域存取權的詳細資訊，請參閱控制個別同盟網域的存取。</span><span class="sxs-lookup"><span data-stu-id="cca63-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="cca63-112">使用控制台啟用或停用封存免責聲明</span><span class="sxs-lookup"><span data-stu-id="cca63-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="cca63-113">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="cca63-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cca63-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="cca63-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="cca63-115">在左導覽列中，按一下 [ **同盟和外部存取**]，然後按一下 [ **Access Edge** 設定]。</span><span class="sxs-lookup"><span data-stu-id="cca63-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="cca63-116">在 [ **Access Edge** 設定] 索引標籤上，依序按一下 [ **全域**]、[ **編輯**] 和 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="cca63-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="cca63-117">在 [ **編輯 Access Edge** 設定] 的 [ **啟用同盟和公用 IM** 連線] 下，選取或清除 [將封存 **免責聲明傳送給同盟夥伴** ] 核取方塊，以啟用或停用自動傳送封存免責聲明。</span><span class="sxs-lookup"><span data-stu-id="cca63-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="cca63-118">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="cca63-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="cca63-119">使用 Windows PowerShell 啟用或停用封存免責聲明</span><span class="sxs-lookup"><span data-stu-id="cca63-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="cca63-120">若要啟用封存免責聲明，請將 **EnableArchivingDisclaimer** 屬性的值設為 True ($True) ：</span><span class="sxs-lookup"><span data-stu-id="cca63-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="cca63-121">若要停用封存免責聲明，請將 **EnableArchivingDisclaimer** 屬性的值設為 False ($False) ：</span><span class="sxs-lookup"><span data-stu-id="cca63-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


