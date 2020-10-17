---
title: Lync Server 2013：修改現有的 Web 服務設定
description: Lync Server 2013：修改現有的 Web 服務設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 455ddf60d171fe584115d646b16f63595285a906
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566989"
---
# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="53bcd-103">在 Lync Server 2013 中修改現有的 Web 服務設定</span><span class="sxs-lookup"><span data-stu-id="53bcd-103">Modify existing Web Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53bcd-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="53bcd-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="53bcd-105">您可以使用 [ **Web 服務** ] 頁面來設定驗證方法，以存取 Lync Server 2013 相關的網頁伺服器和 web 服務。</span><span class="sxs-lookup"><span data-stu-id="53bcd-105">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="53bcd-106">請遵循下列步驟來修改現有的 Web 服務原則。</span><span class="sxs-lookup"><span data-stu-id="53bcd-106">Follow these steps to modify an existing Web Service policy.</span></span>

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="53bcd-107">修改現有的 Web 服務設定</span><span class="sxs-lookup"><span data-stu-id="53bcd-107">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="53bcd-108">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="53bcd-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="53bcd-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="53bcd-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="53bcd-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="53bcd-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="53bcd-111">在左導覽列中，按一下 [ **安全性** ]，然後按一下 [ **Web 服務**]。</span><span class="sxs-lookup"><span data-stu-id="53bcd-111">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="53bcd-112">在 [ **Web 服務** ] 頁面上，按一下設定，然後按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="53bcd-112">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="53bcd-113">在 [ **編輯 Web 服務] 設定**的 **整合式 windows 驗證**中，選取 [ **協商**]、[ **整合式 windows 驗證**] 或 [ **無**]。</span><span class="sxs-lookup"><span data-stu-id="53bcd-113">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="53bcd-114">根據用戶端的功能和您環境中的支援，選取下列其中一項或多項：</span><span class="sxs-lookup"><span data-stu-id="53bcd-114">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="53bcd-115">**啟用 Pin 驗證** ，以允許使用 pin 碼驗證用戶端。</span><span class="sxs-lookup"><span data-stu-id="53bcd-115">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="53bcd-116">[**啟用憑證驗證**] 以讓集區中的伺服器對用戶端發出憑證。</span><span class="sxs-lookup"><span data-stu-id="53bcd-116">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="53bcd-117">[**啟用憑證鏈下載**] 可讓顯示驗證憑證的伺服器下載該憑證的憑證鏈。</span><span class="sxs-lookup"><span data-stu-id="53bcd-117">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="53bcd-118">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="53bcd-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="53bcd-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="53bcd-119">See Also</span></span>


[<span data-ttu-id="53bcd-120">在 Lync Server 2013 控制台中設定驗證</span><span class="sxs-lookup"><span data-stu-id="53bcd-120">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

