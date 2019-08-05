---
title: 在商務用 Skype Server 中刪除 PIN 原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: '摘要: 針對商務用 Skype Server, 刪除使用者的電話撥入式會議 PIN。'
ms.openlocfilehash: 2f42531480ac4099d574a21a96f1954abc70d1d3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189667"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="dc107-103">在商務用 Skype Server 中刪除 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="dc107-103">Delete a PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="dc107-104">**摘要:** 針對商務用 Skype Server, 刪除使用者的電話撥入式會議 PIN。</span><span class="sxs-lookup"><span data-stu-id="dc107-104">**Summary:** Delete a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="dc107-105">請依照下列步驟刪除個人識別碼 (PIN) 原則。</span><span class="sxs-lookup"><span data-stu-id="dc107-105">Follow these steps to delete a personal identification number (PIN) policy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc107-106">您無法刪除全域 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="dc107-106">You cannot delete the global PIN policy.</span></span> 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="dc107-107">在商務用 Skype Server [控制台] 中刪除 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="dc107-107">To delete a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="dc107-108">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.</span><span class="sxs-lookup"><span data-stu-id="dc107-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="dc107-109">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="dc107-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="dc107-110">在左側導覽列中, 按一下 [**安全性**], 然後按一下 [ **PIN 規則**]。</span><span class="sxs-lookup"><span data-stu-id="dc107-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="dc107-111">在 [ **PIN 原則**] 頁面上, 于 [搜尋] 欄位中, 輸入您要刪除之原則的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="dc107-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="dc107-112">在原則清單中, 按一下您想要的原則, 按一下 [**編輯**], 然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="dc107-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="dc107-113">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dc107-113">Click **OK**.</span></span>
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dc107-114">使用 Windows PowerShell Cmdlet 移除 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="dc107-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="dc107-115">您可以使用 Windows PowerShell 與 Remove CsPinPolicy Cmdlet 來刪除 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="dc107-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="dc107-116">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dc107-116">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dc107-117">如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料, 請參閱博客文章[: 「快速入門: 使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="dc107-117">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="dc107-118">在商務用 Skype 伺服器中, 程式是一樣的。</span><span class="sxs-lookup"><span data-stu-id="dc107-118">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="dc107-119">移除特定的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="dc107-119">To remove a specific PIN policy</span></span>

- <span data-ttu-id="dc107-120">這個命令會移除具有身分識別 RedmondPinPolicy 的 PIN 原則:</span><span class="sxs-lookup"><span data-stu-id="dc107-120">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
  ```
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="dc107-121">若要移除所有套用至網站範圍的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="dc107-121">To remove all the PIN policies applied to the site scope</span></span>

- <span data-ttu-id="dc107-122">這個命令會移除在網站範圍中設定的所有 PIN 原則:</span><span class="sxs-lookup"><span data-stu-id="dc107-122">This command removes all the PIN policies configured at the site scope:</span></span>
    
  ```
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="dc107-123">若要移除所有允許使用常見模式的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="dc107-123">To remove all the PIN policies that allow the use of common patterns</span></span>

- <span data-ttu-id="dc107-124">如此一來, 會移除所有允許使用常見模式的 PIN 原則: G</span><span class="sxs-lookup"><span data-stu-id="dc107-124">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
  ```
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

<span data-ttu-id="dc107-125">如需詳細資訊, 請參閱[Remove CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="dc107-125">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  

