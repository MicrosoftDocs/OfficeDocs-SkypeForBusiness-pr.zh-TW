---
title: Lync Server 2013： 為 Director 設定憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e036073f3e617bff993bd38b356d3ac76f73d57
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a><span data-ttu-id="e5b18-102">Lync Server 2013 中 director 設定憑證</span><span class="sxs-lookup"><span data-stu-id="e5b18-102">Configure certificates for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5b18-103">_**主題上次修改日期：** 2012年-09-08_</span><span class="sxs-lookup"><span data-stu-id="e5b18-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e5b18-104">當您執行 [憑證精靈] 時，請確定您用來登入的帳戶，是具有您要使用之憑證範本類型適當權限的群組成員。</span><span class="sxs-lookup"><span data-stu-id="e5b18-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="e5b18-105">根據預設，Lync Server 2013 的憑證要求會使用 [網頁伺服器憑證範本]。</span><span class="sxs-lookup"><span data-stu-id="e5b18-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="e5b18-106">如果您要以 RTCUniversalServerAdmins 群組成員的帳戶使用此範本來要求憑證，請確定群組具有使用該範本所需的註冊權限。</span><span class="sxs-lookup"><span data-stu-id="e5b18-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="e5b18-107">每個 Director 都需要預設憑證、Web 內部憑證以及 Web 外部憑證。</span><span class="sxs-lookup"><span data-stu-id="e5b18-107">Each Director requires a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="e5b18-108">如需 Director 的憑證需求的詳細資訊，請參閱規劃文件中的[Lync Server 2013 中的內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="e5b18-108">For details about the certificate requirements for Directors, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="e5b18-p103">請使用下列程序設定 Director 憑證。為每個 Director 重複這個程序。此程序步驟說明如何從組織部署之內部企業根憑證授權單位 (CA) 設定憑證，以及使用離線要求程序設定憑證。如需從外部 CA 取得憑證的詳細資訊，請洽詢您的支援小組。</span><span class="sxs-lookup"><span data-stu-id="e5b18-p103">Use the following procedure to configure Director certificates. Repeat the procedure for each Director. The steps of this procedure describe how to configure a certificate from an Internal Enterprise Root certification authority (CA) deployed by your organization and with offline request processing. For details about obtaining certificates from an external CA, contact your support team.</span></span>

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a><span data-ttu-id="e5b18-113">為 Director 或 Director 集區設定憑證</span><span class="sxs-lookup"><span data-stu-id="e5b18-113">To configure certificates for the Director or Director pool</span></span>

1.  <span data-ttu-id="e5b18-114">在 Lync Server 部署精靈中下, 一步] 為**步驟 3： 要求、 安裝或指派憑證**，按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="e5b18-114">In the Lync Server Deployment Wizard, next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span>

2.  <span data-ttu-id="e5b18-115">在 **[憑證精靈]** 頁面中，按一下 **[要求]**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-115">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="e5b18-116">在 **[憑證要求]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-116">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="e5b18-117">在「延遲或立即要求」\*\*\*\* 頁面上，接受預設的 [立即將此要求傳送到線上憑證授權單位]\*\*\*\* 選項，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e5b18-117">On the **Delayed or Immediate Requests** page, accept the default **Send the request immediately to an online certification authority** option, and then click **Next**.</span></span>

5.  <span data-ttu-id="e5b18-118">在 **[選擇憑證授權單位 (CA)]** 頁面上，按一下您要使用的內部 Windows 憑證授權單位，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-118">On the **Choose a Certification Authority (CA)** page, click the internal Windows certification authority that you want to use, and then click **Next**.</span></span>

6.  <span data-ttu-id="e5b18-119">在 **[憑證授權單位帳戶]** 頁面上，指定若您據以登入的帳戶不具備要求憑證的充分授權時，要使用的其他憑證，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-119">On the **Certification Authority Account** page, specify alternate credentials to be used if the account you are logged on with does not have sufficient authority to request the certificate, and then click **Next**.</span></span>

7.  <span data-ttu-id="e5b18-120">在 **[指定其他憑證範本]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-120">On the **Specify Alternate Certificate Template** page, click **Next**.</span></span>

8.  <span data-ttu-id="e5b18-121">在 **[名稱和安全性設定]** 頁面上，您可指定 **[易記名稱]**、接受 2048 位元金鑰長度，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-121">On the **Name and Security Settings** page, you can specify a **Friendly Name**, accept the 2048-bit key length, and then click **Next**.</span></span>

9.  <span data-ttu-id="e5b18-122">在 **[組織資訊]** 頁面上，您可選擇性指定組織資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-122">On the **Organization Information** page, optionally specify organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="e5b18-123">在 **[地理資訊]** 頁面上，您可選擇性指定地理資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-123">On the **Geographical Information** page, optionally specify geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="e5b18-124">在 **[主體名稱 / 主體替代名稱]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-124">On the **Subject Name / Subject Alternative Names** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e5b18-125">主體替代名稱清單應該包含您安裝 Director 的電腦名稱 (若是單一 Director) 或 Director 集區名稱，以及為組織設定的簡單 URL 名稱。</span><span class="sxs-lookup"><span data-stu-id="e5b18-125">The subject alternative name list should contain the name of the computer on which you are installing the Director (if a single Director) or the Director pool name, and the simple URL names configured for the organization.</span></span>

    
    </div>

12. <span data-ttu-id="e5b18-126">在「主體別名 (SAN) 上的 SIP 網域設定」\*\*\*\* 頁面上，為您要 Director 處理的所有網域選取 [設定的 SIP 網域]\*\*\*\*，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the **Configured SIP Domains** for all domains that you want the Director to handle, and then click **Next**.</span></span>

13. <span data-ttu-id="e5b18-127">在 **[設定其他主體替代名稱]** 頁面上，增加其他必要的主體替代名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-127">On the **Configure Additional Subject Alternative Names** page, add any additional required subject alternative names, and then click **Next**.</span></span>

14. <span data-ttu-id="e5b18-128">在 **[憑證要求摘要]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-128">On the **Certificate Request Summary** page, click **Next**.</span></span>

15. <span data-ttu-id="e5b18-129">在 **[執行命令]** 頁面上，等命令完成執行後，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-129">On the **Executing Commands** page, click **Next** after the commands have finished running.</span></span>

16. <span data-ttu-id="e5b18-130">在 **[線上憑證要求狀態]** 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-130">On the **Online Certificate Request Status** page, click **Finish**.</span></span>

17. <span data-ttu-id="e5b18-131">在 **[憑證指派]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-131">On the **Certificate Assignment** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e5b18-132">如果您要檢視憑證，請按兩下清單中的憑證。</span><span class="sxs-lookup"><span data-stu-id="e5b18-132">if you want to view the certificate, double-click the certificate in the list.</span></span>

    
    </div>

18. <span data-ttu-id="e5b18-133">在 **[憑證指派摘要]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-133">On the **Certificate Assignment Summary** page, click **Next**.</span></span>

19. <span data-ttu-id="e5b18-134">在 **[執行命令]** 頁面上，等命令完成執行後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-134">On the **Executing Commands** page, click **Finish** after the commands have finished running.</span></span>

20. <span data-ttu-id="e5b18-135">在 **[憑證精靈]** 頁面中，按一下 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-135">On the **Certificate Wizard** page, click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

