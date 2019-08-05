---
title: 重設外部使用者存取的全域原則
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您無法完全刪除全域原則。 在全域原則上使用 [**刪除**] 選項時, 只會將全域原則重設為預設設定, 而不包含任何外部使用者存取選項的支援。
ms.openlocfilehash: 339ad22e1d049510416bfc3433c6c8a104455504
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188800"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="e173f-104">在商務用 Skype Server 中重設外部使用者存取的全域原則</span><span class="sxs-lookup"><span data-stu-id="e173f-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="e173f-105">如果您已建立或設定您不想再使用的外部使用者存取原則, 您可以執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="e173f-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="e173f-106">刪除您建立的任何網站或使用者原則。</span><span class="sxs-lookup"><span data-stu-id="e173f-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="e173f-107">將全域原則重設為預設設定。</span><span class="sxs-lookup"><span data-stu-id="e173f-107">Reset the global policy to the default settings.</span></span> <span data-ttu-id="e173f-108">預設全域原則設定會拒絕任何外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="e173f-108">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="e173f-109">無法刪除全域原則。</span><span class="sxs-lookup"><span data-stu-id="e173f-109">The global policy cannot be deleted.</span></span>

<span data-ttu-id="e173f-110">您無法完全刪除全域原則。</span><span class="sxs-lookup"><span data-stu-id="e173f-110">You cannot completely delete a global policy.</span></span> <span data-ttu-id="e173f-111">在全域原則上使用 [**刪除**] 選項時, 只會將全域原則重設為預設設定, 而不包含任何外部使用者存取選項的支援。</span><span class="sxs-lookup"><span data-stu-id="e173f-111">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="e173f-112">將全域原則重設為預設設定</span><span class="sxs-lookup"><span data-stu-id="e173f-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="e173f-113">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e173f-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e173f-114">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e173f-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="e173f-115">在左側導覽列中, 按一下 [**外部使用者存取**], 然後按一下 [**外部存取原則**]。</span><span class="sxs-lookup"><span data-stu-id="e173f-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="e173f-116">在 [**外部存取原則**] 索引標籤上, 按一下 [全域原則], 按一下 [**編輯**], 然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="e173f-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="e173f-117">當系統提示您確認刪除時, 請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e173f-117">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="e173f-118">頁面頂端會出現一則訊息, 通知您全域原則已重設。</span><span class="sxs-lookup"><span data-stu-id="e173f-118">A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e173f-119">使用 Windows PowerShell Cmdlet 來重設全域外部存取原則</span><span class="sxs-lookup"><span data-stu-id="e173f-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e173f-120">您可以使用 Windows PowerShell 和 CsExternalAccessPolicy Cmdlet 來重設全域外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="e173f-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="e173f-121">此 Cmdlet 可從商務用 Skype Server Management 命令介面或從遠端會話 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="e173f-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="e173f-122">若要重設全域外部存取原則</span><span class="sxs-lookup"><span data-stu-id="e173f-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="e173f-123">這個命令會重定全域外部存取原則:</span><span class="sxs-lookup"><span data-stu-id="e173f-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="e173f-124">如需詳細資訊, 請參閱[Remove CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="e173f-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>


