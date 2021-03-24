---
title: 重設外部使用者存取的全域原則
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您無法完全刪除全域原則。使用全域原則的 **[刪除]** 選項只會將全域原則重設為預設設定，而預設設定不包含對任何外部使用者存取選項的支援。
ms.openlocfilehash: 6c74690d86f7a300b79b755db7c6111eec7810f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098969"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="da590-104">在商務用 Skype Server 中重設外部使用者存取的全域原則</span><span class="sxs-lookup"><span data-stu-id="da590-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="da590-105">如果您已建立或設定不想再使用的外部使用者存取原則，則可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="da590-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="da590-106">刪除任何已建立的網站或使用者原則。</span><span class="sxs-lookup"><span data-stu-id="da590-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="da590-p102">將全域原則重設為預設設定。預設全域原則設定拒絕任何外部使用者存取。全域原則無法刪除。</span><span class="sxs-lookup"><span data-stu-id="da590-p102">Reset the global policy to the default settings. The default global policy settings deny any external user access. The global policy cannot be deleted.</span></span>

<span data-ttu-id="da590-p103">您無法完全刪除全域原則。使用全域原則的 **[刪除]** 選項只會將全域原則重設為預設設定，而預設設定不包含對任何外部使用者存取選項的支援。</span><span class="sxs-lookup"><span data-stu-id="da590-p103">You cannot completely delete a global policy. Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="da590-112">若要將全域原則重設為預設設定</span><span class="sxs-lookup"><span data-stu-id="da590-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="da590-113">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="da590-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="da590-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="da590-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="da590-115">在左導覽列中，依序按一下 **[外部使用者存取]** 和 **[外部存取原則]**。</span><span class="sxs-lookup"><span data-stu-id="da590-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="da590-116">在 **[外部存取原則]** 索引標籤上，依序按一下全域原則、**[編輯]** 和 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="da590-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="da590-p104">系統提示確認刪除時，請按一下 [確定] 。頁面頂端會出現一則訊息，通知您已將全域原則重設。</span><span class="sxs-lookup"><span data-stu-id="da590-p104">When prompted to confirm the deletion, click **OK**. A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="da590-119">使用 Windows PowerShell Cmdlet 重設全域外部存取原則</span><span class="sxs-lookup"><span data-stu-id="da590-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="da590-120">您可以使用 Windows PowerShell 和 Remove-CsExternalAccessPolicy Cmdlet 來重設全域外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="da590-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="da590-121">您可以從商務用 Skype Server 管理命令介面或從遠端會話 Windows PowerShell 執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="da590-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="da590-122">重設全域外部存取原則</span><span class="sxs-lookup"><span data-stu-id="da590-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="da590-123">這個命令可重設全域外部存取原則：</span><span class="sxs-lookup"><span data-stu-id="da590-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="da590-124">如需詳細資訊，請參閱 [get-csexternalaccesspolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="da590-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>