---
title: 在商務用 Skype Server 中查看會議配置設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 摘要：瞭解如何在商務用 Skype Server 中查看會議配置設定。
ms.openlocfilehash: 81f5ef1bc0ce28c7741aa99529e7ba107ff4127f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096699"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="68336-103">在商務用 Skype Server 中查看會議配置設定</span><span class="sxs-lookup"><span data-stu-id="68336-103">View meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="68336-104">**摘要：** 瞭解如何在商務用 Skype Server 中查看會議配置設定。</span><span class="sxs-lookup"><span data-stu-id="68336-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="68336-105">您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面來查看會議設定設定。</span><span class="sxs-lookup"><span data-stu-id="68336-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="68336-106">使用商務用 Skype Server 控制台來查看會議設定設定</span><span class="sxs-lookup"><span data-stu-id="68336-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="68336-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="68336-107"><a name="BKMK_ViewJoinSettings"> </a></span></span>

1. <span data-ttu-id="68336-108">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="68336-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="68336-109">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="68336-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="68336-110">在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議** 設定]。</span><span class="sxs-lookup"><span data-stu-id="68336-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="68336-111">在 [ **會議** 設定] 頁面上，按一下您要查看的會議設定。</span><span class="sxs-lookup"><span data-stu-id="68336-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="68336-112">在 [ **編輯檔案篩選**] 中，選取 [ **顯示詳細資料** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="68336-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="68336-113">**編輯會議設定- \<policy\>** 開啟顯示選取原則的設定。</span><span class="sxs-lookup"><span data-stu-id="68336-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="68336-114">如需設定設定的詳細資訊，請參閱 [在商務用 Skype Server 中建立會議配置設定](create-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="68336-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="68336-115">使用商務用 Skype Server 管理命令介面來查看會議配置設定</span><span class="sxs-lookup"><span data-stu-id="68336-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="68336-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="68336-116"><a name="BKMK_ViewJoinSettings"> </a></span></span>

<span data-ttu-id="68336-117">若要查看所有會議設定設定的相關資訊，請使用 **Get-CsMeetingConfiguration** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="68336-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="68336-118">此命令會傳回類似下列的資訊：</span><span class="sxs-lookup"><span data-stu-id="68336-118">This command will return information similar to the following:</span></span>
  
<pre>
Identity                        : Global
PstnCallersBypassLobby          : True
EnableAssignedConferenceType    : True
DesignateAsPresenter            : Company
AssignedConferenceTypeByDefault : True
AdmitAnonymousUsersByDefault    : True
RequireRoomSystemsAuthorization : False
LogoURL                         :
LegalURL                        :
HelpURL                         :
CustomFooterText                :
AllowConferenceRecording        : True
</pre>

<span data-ttu-id="68336-119">如需詳細資訊，包括完整的參數清單，請參閱 [Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="68336-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
