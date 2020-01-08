---
title: Lync Server 2013：為 Director 設定憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d2da30923231087e706e2a969fdba2884361f6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a><span data-ttu-id="acf64-102">在 Lync Server 2013 中設定 Director 的憑證</span><span class="sxs-lookup"><span data-stu-id="acf64-102">Configure certificates for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acf64-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="acf64-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="acf64-104">當您執行證書嚮導時，請確定您使用的帳戶是群組的成員，而該群組已獲指派您要使用之憑證範本類型的適當許可權。</span><span class="sxs-lookup"><span data-stu-id="acf64-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="acf64-105">根據預設，Lync Server 2013 證書要求會使用 Web 服務器憑證範本。</span><span class="sxs-lookup"><span data-stu-id="acf64-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="acf64-106">如果您使用的帳戶是 RTCUniversalServerAdmins 群組的成員，以使用此範本來申請憑證，請確認該群組已獲指派使用該範本所需的 [註冊] 許可權。</span><span class="sxs-lookup"><span data-stu-id="acf64-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="acf64-107">每個控制器都需要預設憑證、網頁內部憑證及網頁外部憑證。</span><span class="sxs-lookup"><span data-stu-id="acf64-107">Each Director requires a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="acf64-108">如需控制器的憑證需求的詳細資料，請參閱規劃檔中的[Lync Server 2013 內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="acf64-108">For details about the certificate requirements for Directors, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="acf64-109">使用下列程式來設定控制器憑證。</span><span class="sxs-lookup"><span data-stu-id="acf64-109">Use the following procedure to configure Director certificates.</span></span> <span data-ttu-id="acf64-110">針對每個主管重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="acf64-110">Repeat the procedure for each Director.</span></span> <span data-ttu-id="acf64-111">此程式的步驟說明如何從貴組織部署的內部企業根憑證授權單位（CA）及離線要求處理來設定憑證。</span><span class="sxs-lookup"><span data-stu-id="acf64-111">The steps of this procedure describe how to configure a certificate from an Internal Enterprise Root certification authority (CA) deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="acf64-112">如需從外部 CA 取得憑證的詳細資料，請與您的支援小組聯繫。</span><span class="sxs-lookup"><span data-stu-id="acf64-112">For details about obtaining certificates from an external CA, contact your support team.</span></span>

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a><span data-ttu-id="acf64-113">為主管或主管池設定憑證</span><span class="sxs-lookup"><span data-stu-id="acf64-113">To configure certificates for the Director or Director pool</span></span>

1.  <span data-ttu-id="acf64-114">在 Lync Server 部署嚮導中，在 [**步驟3：要求、安裝或指派憑證**] 旁，按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="acf64-114">In the Lync Server Deployment Wizard, next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span>

2.  <span data-ttu-id="acf64-115">在 [**憑證] 嚮導**頁面上，按一下 [**要求**]。</span><span class="sxs-lookup"><span data-stu-id="acf64-115">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="acf64-116">在 [**憑證要求**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="acf64-116">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="acf64-117">在 [**延遲] 或 [立即要求**] 頁面上，接受預設將**要求立即傳送給線上憑證授權單位**選項，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="acf64-117">On the **Delayed or Immediate Requests** page, accept the default **Send the request immediately to an online certification authority** option, and then click **Next**.</span></span>

5.  <span data-ttu-id="acf64-118">在 [**選擇憑證授權單位（CA）** ] 頁面上，按一下您要使用的內部 Windows 憑證授權單位，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="acf64-118">On the **Choose a Certification Authority (CA)** page, click the internal Windows certification authority that you want to use, and then click **Next**.</span></span>

6.  <span data-ttu-id="acf64-119">在 [**認證機構帳戶**] 頁面上，指定您登入的帳戶沒有足夠的授權來要求憑證，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="acf64-119">On the **Certification Authority Account** page, specify alternate credentials to be used if the account you are logged on with does not have sufficient authority to request the certificate, and then click **Next**.</span></span>

7.  <span data-ttu-id="acf64-120">在 [**指定備用憑證範本**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="acf64-120">On the **Specify Alternate Certificate Template** page, click **Next**.</span></span>

8.  <span data-ttu-id="acf64-121">在 [**名稱及安全性設定**] 頁面上，您可以指定**易記名稱**、接受2048位金鑰長度，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="acf64-121">On the **Name and Security Settings** page, you can specify a **Friendly Name**, accept the 2048-bit key length, and then click **Next**.</span></span>

9.  <span data-ttu-id="acf64-122">在 [**組織資訊**] 頁面上，選擇 [指定組織資訊]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="acf64-122">On the **Organization Information** page, optionally specify organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="acf64-123">在 [**地理資訊**] 頁面上，選擇 [指定地理資訊]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="acf64-123">On the **Geographical Information** page, optionally specify geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="acf64-124">在 [ **Subject 名稱/Subject 替換名稱**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="acf64-124">On the **Subject Name / Subject Alternative Names** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="acf64-125">[Subject 替換名稱] 清單應包含您要安裝控制器的電腦名稱稱（如果是單一控制器）或主管池名稱，以及為組織設定的簡單 URL 名稱。</span><span class="sxs-lookup"><span data-stu-id="acf64-125">The subject alternative name list should contain the name of the computer on which you are installing the Director (if a single Director) or the Director pool name, and the simple URL names configured for the organization.</span></span>

    
    </div>

12. <span data-ttu-id="acf64-126">在 [**受領人替代名稱（san）** ] 頁面上的 [SIP 網域設定] 上，針對您想要讓控制器處理的所有網域，選取**已設定的 SIP 網域**，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="acf64-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the **Configured SIP Domains** for all domains that you want the Director to handle, and then click **Next**.</span></span>

13. <span data-ttu-id="acf64-127">在 [**設定其他消費者備用名稱**] 頁面上，新增任何其他必要的消費者替換名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="acf64-127">On the **Configure Additional Subject Alternative Names** page, add any additional required subject alternative names, and then click **Next**.</span></span>

14. <span data-ttu-id="acf64-128">在 [**憑證要求摘要**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="acf64-128">On the **Certificate Request Summary** page, click **Next**.</span></span>

15. <span data-ttu-id="acf64-129">在 [**執行命令**] 頁面上，在命令執行完畢後，按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="acf64-129">On the **Executing Commands** page, click **Next** after the commands have finished running.</span></span>

16. <span data-ttu-id="acf64-130">在 [**線上憑證要求狀態**] 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="acf64-130">On the **Online Certificate Request Status** page, click **Finish**.</span></span>

17. <span data-ttu-id="acf64-131">在 [**憑證指派**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="acf64-131">On the **Certificate Assignment** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="acf64-132">如果您想要查看憑證，請按兩下清單中的憑證。</span><span class="sxs-lookup"><span data-stu-id="acf64-132">if you want to view the certificate, double-click the certificate in the list.</span></span>

    
    </div>

18. <span data-ttu-id="acf64-133">在 [**憑證指派摘要**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="acf64-133">On the **Certificate Assignment Summary** page, click **Next**.</span></span>

19. <span data-ttu-id="acf64-134">在 [**執行命令**] 頁面上，在命令完成執行之後，按一下 **[完成]** 。</span><span class="sxs-lookup"><span data-stu-id="acf64-134">On the **Executing Commands** page, click **Finish** after the commands have finished running.</span></span>

20. <span data-ttu-id="acf64-135">在 [**憑證] 嚮導**頁面上，按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="acf64-135">On the **Certificate Wizard** page, click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

