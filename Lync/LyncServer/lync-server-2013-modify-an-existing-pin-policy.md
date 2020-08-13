---
title: Lync Server 2013：修改現有的 PIN 原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify an existing PIN policy
ms:assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520993(v=OCS.15)
ms:contentKeyID: 48184143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99f77fd153b9c4a111504ac16737527cb68b1ad7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-an-existing-pin-policy-in-lync-server-2013"></a><span data-ttu-id="aee7c-102">在 Lync Server 2013 中修改現有的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="aee7c-102">Modify an existing PIN policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aee7c-103">_**主題上次修改日期：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="aee7c-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="aee7c-104">您可以使用 [ **PIN 原則**] 索引標籤，為使用 IP 電話連接至 Lync 2013 的使用者提供個人識別碼 (PIN) 驗證。</span><span class="sxs-lookup"><span data-stu-id="aee7c-104">You can use the **PIN Policy** tab to provide personal identification number (PIN) authentication to users who are connecting to Lync 2013 with IP Phones.</span></span> <span data-ttu-id="aee7c-105">若要使用 PIN 驗證，請確定已在 Web 服務設定中選取了 [啟用 PIN 驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aee7c-105">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span> <span data-ttu-id="aee7c-106">如需詳細資訊，請參閱[在 Lync Server 2013 中修改現有的 Web 服務設定](lync-server-2013-modify-existing-web-service-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="aee7c-106">For details, see [Modify existing Web Service configuration settings in Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span></span>

<span data-ttu-id="aee7c-107">請遵循下列步驟來修改使用者層級或網站層級的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="aee7c-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span>

<div>

## <a name="to-modify-an-existing-pin-policy"></a><span data-ttu-id="aee7c-108">若要修改現有的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="aee7c-108">To modify an existing PIN policy</span></span>

1.  <span data-ttu-id="aee7c-109">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="aee7c-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="aee7c-110">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="aee7c-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aee7c-111">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="aee7c-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aee7c-112">在左導覽列中，依序按一下 [安全性]\*\*\*\* 和 [PIN 原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aee7c-112">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="aee7c-113">在 **[PIN 原則]** 頁面上，依序按一下原則、**[編輯]** 和 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="aee7c-113">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="aee7c-p103">在 **[編輯 PIN 原則]** 的 **[最小 PIN 長度]** 中，輸入或選取您要允許的最小 PIN 長度。預設的最小長度為五位數。</span><span class="sxs-lookup"><span data-stu-id="aee7c-p103">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>

6.  <span data-ttu-id="aee7c-p104">若要能夠指定使用者遭鎖定前可嘗試登入的次數上限，請選取 **[指定登入嘗試次數上限]** 核取方塊。若未選取此選項，則會根據 PIN 長度自動指定允許的嘗試次數上限。依預設會自動指定嘗試次數上限。</span><span class="sxs-lookup"><span data-stu-id="aee7c-p104">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>

7.  <span data-ttu-id="aee7c-119">如果您選取了 **[指定登入嘗試次數上限]** 核取方塊，請在 **[登入嘗試次數上限]** 中輸入或選取您所要允許的登入嘗試次數上限。</span><span class="sxs-lookup"><span data-stu-id="aee7c-119">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

8.  <span data-ttu-id="aee7c-p105">若要讓 PIN 有期限，請選取 **[啟用 PIN 到期]** 核取方塊。若未選取此選項，PIN 將永不過期。根據預設，PIN 永遠不會過期。</span><span class="sxs-lookup"><span data-stu-id="aee7c-p105">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>

9.  <span data-ttu-id="aee7c-123">如果您選取了 **[啟用 PIN 到期]** 核取方塊，請在 **[PIN 於下列日數後到期]** 中輸入或選取 PIN 將在幾天之後到期。</span><span class="sxs-lookup"><span data-stu-id="aee7c-123">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

10. <span data-ttu-id="aee7c-p106">在 **[PIN 碼歷程記錄計數]** 中，輸入使用者必須在建立多少個 PIN 之後才可重複使用 PIN。根據預設，使用者可重複使用其 PIN。</span><span class="sxs-lookup"><span data-stu-id="aee7c-p106">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>

11. <span data-ttu-id="aee7c-p107">若要允許在 PIN 中使用共同模式的數字 (如連續數字與重複數字組)，請選取 **[允許共同模式]** 核取方塊。若未選取此選項，則只會允許複合模式的數字。依預設只會允許複合模式的數字。</span><span class="sxs-lookup"><span data-stu-id="aee7c-p107">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="aee7c-129">建議您不要允許共同模式。</span><span class="sxs-lookup"><span data-stu-id="aee7c-129">We recommend that you do not allow common patterns.</span></span>

    
    </div>

12. <span data-ttu-id="aee7c-130">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="aee7c-130">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

