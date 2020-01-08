---
title: Lync Server 2013：修改現有的 Web 服務設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f53d0eb34412c746332a0f74d140b6c41c9c257f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="dfb73-102">在 Lync Server 2013 中修改現有的 Web 服務配置設定</span><span class="sxs-lookup"><span data-stu-id="dfb73-102">Modify existing Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfb73-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dfb73-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dfb73-104">您可以使用 [ **Web 服務**] 頁面來設定存取 Lync Server 2013 相關 web 伺服器與 web 服務的驗證方法。</span><span class="sxs-lookup"><span data-stu-id="dfb73-104">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="dfb73-105">請依照這些步驟來修改現有的 Web 服務原則。</span><span class="sxs-lookup"><span data-stu-id="dfb73-105">Follow these steps to modify an existing Web Service policy.</span></span>

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="dfb73-106">修改現有的 Web 服務設定</span><span class="sxs-lookup"><span data-stu-id="dfb73-106">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="dfb73-107">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="dfb73-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="dfb73-108">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="dfb73-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dfb73-109">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="dfb73-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dfb73-110">在左側導覽列中，按一下 [**安全性**]，然後按一下 [ **Web 服務**]。</span><span class="sxs-lookup"><span data-stu-id="dfb73-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="dfb73-111">在 [ **Web 服務**] 頁面上，按一下 [設定]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="dfb73-111">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="dfb73-112">在 [**編輯 Web 服務**] 中，在**整合的 windows 驗證**中，選取 [**協商**]、[**整合式 windows 驗證**] 或 [**無**]。</span><span class="sxs-lookup"><span data-stu-id="dfb73-112">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="dfb73-113">根據您的環境中用戶端和支援的功能，選取下列一或多個專案：</span><span class="sxs-lookup"><span data-stu-id="dfb73-113">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="dfb73-114">**啟用 Pin 驗證**，讓用戶端使用 pin 碼進行驗證。</span><span class="sxs-lookup"><span data-stu-id="dfb73-114">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="dfb73-115">**啟用憑證驗證**，將池中的伺服器頒發憑證給用戶端。</span><span class="sxs-lookup"><span data-stu-id="dfb73-115">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="dfb73-116">**啟用憑證連結下載**，讓伺服器提供驗證憑證下載該憑證的憑證鏈。</span><span class="sxs-lookup"><span data-stu-id="dfb73-116">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="dfb73-117">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dfb73-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dfb73-118">請參閱</span><span class="sxs-lookup"><span data-stu-id="dfb73-118">See Also</span></span>


<span data-ttu-id="dfb73-119">[在 Lync Server 2013 [控制台] 中設定驗證](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)</span><span class="sxs-lookup"><span data-stu-id="dfb73-119">[Configuring authentication in the Lync Server 2013 Control Panel](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

