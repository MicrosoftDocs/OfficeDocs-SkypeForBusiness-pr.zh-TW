---
title: 在商務用 Skype Server 中查看 PIN 原則資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: '摘要: 針對商務用 Skype Server 查看使用者的 PIN 原則資訊。'
ms.openlocfilehash: 5f6269b766748d5027c0a8182dd027754cd5cc00
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193010"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a><span data-ttu-id="b3015-103">在商務用 Skype Server 中查看 PIN 原則資訊</span><span class="sxs-lookup"><span data-stu-id="b3015-103">View PIN policy information in Skype for Business Server</span></span>
 
<span data-ttu-id="b3015-104">**摘要:** 針對商務用 Skype Server, 查看使用者的 PIN 原則資訊。</span><span class="sxs-lookup"><span data-stu-id="b3015-104">**Summary:** View a user's PIN policy information for Skype for Business Server.</span></span>
  
<span data-ttu-id="b3015-105">您可以使用 [**釘選原則**] 索引標籤來查看使用 IP 電話連線至商務用 Skype 的使用者個人識別碼 (pin) 驗證。</span><span class="sxs-lookup"><span data-stu-id="b3015-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="b3015-106">若要使用 PIN 驗證, 請確認已在 [Web 服務設定] 中選取 [**啟用 Pin 驗證**]。</span><span class="sxs-lookup"><span data-stu-id="b3015-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="b3015-107">請依照這些步驟來修改使用者層級或網站層級的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="b3015-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="b3015-108">若要在商務用 Skype Server [控制台] 中查看 PIN 原則的相關資訊</span><span class="sxs-lookup"><span data-stu-id="b3015-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="b3015-109">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.</span><span class="sxs-lookup"><span data-stu-id="b3015-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="b3015-110">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="b3015-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b3015-111">在左側導覽列中, 按一下 [**安全性**], 然後按一下 [ **PIN 規則**]。</span><span class="sxs-lookup"><span data-stu-id="b3015-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="b3015-112">在 [ **PIN 原則**] 頁面上, 按一下原則, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="b3015-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b3015-113">使用 Windows PowerShell Cmdlet 來查看 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="b3015-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b3015-114">您也可以使用 Windows PowerShell 和 CsPinPolicy Cmdlet 來查看 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="b3015-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="b3015-115">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b3015-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b3015-116">如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料, 請參閱博客文章[: 「快速入門: 使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="b3015-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="b3015-117">在商務用 Skype 伺服器中, 程式是一樣的。</span><span class="sxs-lookup"><span data-stu-id="b3015-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="b3015-118">若要查看 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="b3015-118">To view PIN policies</span></span>

<span data-ttu-id="b3015-119">若要查看所有 PIN 原則的相關資訊, 請在商務用 Skype Server 管理命令介面中輸入下列命令, 然後按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="b3015-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```
  Get-CsPinPolicy
  ```

<span data-ttu-id="b3015-120">這會傳回如下所示的資訊:</span><span class="sxs-lookup"><span data-stu-id="b3015-120">That will return information similar to this:</span></span>

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

<span data-ttu-id="b3015-121">如需詳細資訊, 請參閱[CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="b3015-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b3015-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b3015-122">See also</span></span>

[<span data-ttu-id="b3015-123">在商務用 Skype Server 中建立新的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="b3015-123">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
