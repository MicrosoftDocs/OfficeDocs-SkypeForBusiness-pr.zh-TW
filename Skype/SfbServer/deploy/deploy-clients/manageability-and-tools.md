---
title: Skype 室系統可管理性與工具
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: 若要瞭解 Skype 室系統的管理工具，請閱讀本主題。
ms.openlocfilehash: 74c484b321312fc77c7a1e892f41bdeac8af49ff
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768856"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="1fcee-103">Skype 室系統可管理性與工具</span><span class="sxs-lookup"><span data-stu-id="1fcee-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="1fcee-104">若要瞭解 Skype 室系統的管理工具，請閱讀本主題。</span><span class="sxs-lookup"><span data-stu-id="1fcee-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="1fcee-105">管理入口網站</span><span class="sxs-lookup"><span data-stu-id="1fcee-105">Administrative Portal</span></span>

<span data-ttu-id="1fcee-106">在商務用 Skype Server 內部部署中，您可以使用 Skype 室系統管理入口網站主動管理及監視貴組織內的 Skype 室系統部署。</span><span class="sxs-lookup"><span data-stu-id="1fcee-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="1fcee-107">如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="1fcee-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="1fcee-108">在商務用 Skype Server 中部署 SRS v1 管理網頁入口網站</span><span class="sxs-lookup"><span data-stu-id="1fcee-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a><span data-ttu-id="1fcee-109">Exchange 檢查清單</span><span class="sxs-lookup"><span data-stu-id="1fcee-109">Exchange Checklist</span></span>

- <span data-ttu-id="1fcee-110">確認自動探索已設定，且可供 autodiscover.domain.com 的內部 DNS A/CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="1fcee-110">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="1fcee-111">Ping 自動探索（例如，Ping Autodiscover.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="1fcee-111">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="1fcee-112">使用 Microsoft Connectivity 分析程式工具測試自動探索服務。</span><span class="sxs-lookup"><span data-stu-id="1fcee-112">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="1fcee-113">選擇第一個測試，「我無法使用 Office Outlook 登入。」</span><span class="sxs-lookup"><span data-stu-id="1fcee-113">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="1fcee-114">如果會議室已有資源信箱，請將此帳戶延伸至 Skype 會議室系統（頁面底部的範例腳本）。</span><span class="sxs-lookup"><span data-stu-id="1fcee-114">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="1fcee-115">商務用 Skype 檢查清單</span><span class="sxs-lookup"><span data-stu-id="1fcee-115">Skype for Business Checklist</span></span>

- <span data-ttu-id="1fcee-116">執行下列工具：</span><span class="sxs-lookup"><span data-stu-id="1fcee-116">Run the following tools:</span></span>
    
  - <span data-ttu-id="1fcee-117">商務用 Skype 最佳做法分析工具</span><span class="sxs-lookup"><span data-stu-id="1fcee-117">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="1fcee-118">商務用 Skype 健康情況分析工具（Excel）</span><span class="sxs-lookup"><span data-stu-id="1fcee-118">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="1fcee-119">商務用 Skype 連線分析程式 32-位或64位</span><span class="sxs-lookup"><span data-stu-id="1fcee-119">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="1fcee-120">查看[適用于 Office 365 的實用的新疑難排解及分析工具](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/)。</span><span class="sxs-lookup"><span data-stu-id="1fcee-120">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="1fcee-121">確認您有商務用 Skype 文件庫和 Office Web Apps 伺服器，而且可以使用商務用 Skype 用戶端來共用 PowerPoint 投影片組。</span><span class="sxs-lookup"><span data-stu-id="1fcee-121">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="1fcee-122">如果會議室已有資源信箱，請針對商務用 Skype 啟用該信箱。</span><span class="sxs-lookup"><span data-stu-id="1fcee-122">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="1fcee-123">如有需要，請向 [會議室系統] 要求 [已執行] （電話號碼），並更新 Active Directory 工具中的 [一般電話] 欄位。</span><span class="sxs-lookup"><span data-stu-id="1fcee-123">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="1fcee-124">網路</span><span class="sxs-lookup"><span data-stu-id="1fcee-124">Network</span></span>

- <span data-ttu-id="1fcee-125">請確定您有 Skype 房間系統的有線網路連線。</span><span class="sxs-lookup"><span data-stu-id="1fcee-125">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="1fcee-126">閱讀商務用 Skype 的網路規劃指南。</span><span class="sxs-lookup"><span data-stu-id="1fcee-126">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="1fcee-127">從商務用 Skype 合作夥伴要求商務用 Skype 網路評量。</span><span class="sxs-lookup"><span data-stu-id="1fcee-127">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="1fcee-128">閱讀在商務用 Skype 健康情況分析工具（Excel）中捕獲的效能資料。</span><span class="sxs-lookup"><span data-stu-id="1fcee-128">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="1fcee-129">執行網路分析工具。</span><span class="sxs-lookup"><span data-stu-id="1fcee-129">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="1fcee-130">執行「預撥通話」工具。</span><span class="sxs-lookup"><span data-stu-id="1fcee-130">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="1fcee-131">Skype 室系統安全性</span><span class="sxs-lookup"><span data-stu-id="1fcee-131">Skype Room System Security</span></span>

<span data-ttu-id="1fcee-132">Skype 室系統是內嵌的系統，可使用商務用 Skype 安全模型、版權管理和管理工具（例如 SCOM），在 Windows 部署中完整整合。</span><span class="sxs-lookup"><span data-stu-id="1fcee-132">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="1fcee-133">功能包括：</span><span class="sxs-lookup"><span data-stu-id="1fcee-133">Features include:</span></span>
  
- <span data-ttu-id="1fcee-134">[寫入篩選] 可防止磁片在使用者模式中寫入</span><span class="sxs-lookup"><span data-stu-id="1fcee-134">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="1fcee-135">[應用程式保險箱] 可防止未授權的 app 執行。</span><span class="sxs-lookup"><span data-stu-id="1fcee-135">App Locker to prevent unauthorized apps from running.</span></span> <span data-ttu-id="1fcee-136">所有的 USB 埠在使用者模式中都停用。</span><span class="sxs-lookup"><span data-stu-id="1fcee-136">All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="1fcee-137">沒有任何標準 app 或檢視器位於 Skype 聊天室系統硬體上。</span><span class="sxs-lookup"><span data-stu-id="1fcee-137">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="1fcee-138">所有內容都是透過 HTTP 或 RDP 通訊協定來呈現。</span><span class="sxs-lookup"><span data-stu-id="1fcee-138">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="1fcee-139">裝置電腦會執行 Windows Embedded Standard 7 作業系統。</span><span class="sxs-lookup"><span data-stu-id="1fcee-139">The appliance PC runs the Windows Embedded Standard 7 operating system.</span></span> <span data-ttu-id="1fcee-140">所有硬體（包括裝置）都是由 OEM 合作夥伴提供。</span><span class="sxs-lookup"><span data-stu-id="1fcee-140">All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="1fcee-141">選用網域加入 Active Directory 網域服務（AD DS），啟用本機安全性帳戶管理和控制。</span><span class="sxs-lookup"><span data-stu-id="1fcee-141">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="1fcee-142">您也可以使用商務用 Skype 系統管理中心來管理本機管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="1fcee-142">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="1fcee-143">Skype 室系統會透過標準的 Microsoft 更新程式來更新。</span><span class="sxs-lookup"><span data-stu-id="1fcee-143">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="1fcee-144">Skype 室系統會與商務用 Skype 連線。</span><span class="sxs-lookup"><span data-stu-id="1fcee-144">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="1fcee-145">商務用 Skype 使用端對端加密和授權進行所有通訊模式</span><span class="sxs-lookup"><span data-stu-id="1fcee-145">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="1fcee-146">Skype 室系統支援商務用 Skype 安全性與合規性標準。</span><span class="sxs-lookup"><span data-stu-id="1fcee-146">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="1fcee-147">如需詳細資訊，請參閱[商務用 Skype Server 中的安全性規劃](../../plan-your-deployment/security/security.md)。</span><span class="sxs-lookup"><span data-stu-id="1fcee-147">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="1fcee-148">授權</span><span class="sxs-lookup"><span data-stu-id="1fcee-148">License</span></span>

<span data-ttu-id="1fcee-149">確認您使用 KMS 來啟用軟體。</span><span class="sxs-lookup"><span data-stu-id="1fcee-149">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="1fcee-150">如果是這樣，您可能需要檢查或新增商務用 Skype 用戶端 KMS 金鑰給它。</span><span class="sxs-lookup"><span data-stu-id="1fcee-150">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="1fcee-151">如果您使用的不是 KMS，請要求商務用 Skype 用戶端 MAK 的大量授權金鑰。</span><span class="sxs-lookup"><span data-stu-id="1fcee-151">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="1fcee-152">授權金鑰</span><span class="sxs-lookup"><span data-stu-id="1fcee-152">License keys</span></span>

<span data-ttu-id="1fcee-153">Skype 會議室系統會在背景中執行商務用 Skype 桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="1fcee-153">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="1fcee-154">如果 Skype 室系統是網域成員，就會發現您的 KMS。</span><span class="sxs-lookup"><span data-stu-id="1fcee-154">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="1fcee-155">（如果它有大量授權的 KMS 金鑰，就會自動啟動）。</span><span class="sxs-lookup"><span data-stu-id="1fcee-155">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="1fcee-156">大量授權也會提供 MAK，您可以在此輸入它顯示 xxxxx-xxxxx-xxxxx。</span><span class="sxs-lookup"><span data-stu-id="1fcee-156">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="1fcee-157">（您需要透過網際網路存取才能使用 MAK 啟用，但不是 KMS）。</span><span class="sxs-lookup"><span data-stu-id="1fcee-157">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="1fcee-158">如需詳細資訊，請參閱 Office 2013 的大量啟用。</span><span class="sxs-lookup"><span data-stu-id="1fcee-158">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="1fcee-159">若要進入 MAK 金鑰，請移至 OEM \>設定 SRS 授權工具。</span><span class="sxs-lookup"><span data-stu-id="1fcee-159">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="1fcee-160">按一下 [檢查狀態]。</span><span class="sxs-lookup"><span data-stu-id="1fcee-160">Click Check Status.</span></span> <span data-ttu-id="1fcee-161">當狀態顯示為「產品未啟用」時，請輸入金鑰。</span><span class="sxs-lookup"><span data-stu-id="1fcee-161">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="1fcee-162">如果在啟用期間收到錯誤訊息，指出「「軟體授權服務報告產品金鑰無效」，然後確認：</span><span class="sxs-lookup"><span data-stu-id="1fcee-162">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="1fcee-163">已正確輸入金鑰。</span><span class="sxs-lookup"><span data-stu-id="1fcee-163">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="1fcee-164">您輸入的是商務用 Skype MAK 金鑰，而不是其他金鑰。</span><span class="sxs-lookup"><span data-stu-id="1fcee-164">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="1fcee-165">系統可存取網際網路。</span><span class="sxs-lookup"><span data-stu-id="1fcee-165">The system has Internet access.</span></span>
    
- <span data-ttu-id="1fcee-166">您可以透過電話啟動，但必須先嘗試使用 SRS 授權工具啟動。</span><span class="sxs-lookup"><span data-stu-id="1fcee-166">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="1fcee-167">若要透過電話啟用，請啟動測試會議（不是太短的測試通話）。</span><span class="sxs-lookup"><span data-stu-id="1fcee-167">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="1fcee-168">在 Office 啟用嚮導中，選取 [電話啟用]、[撥打電話 Microsoft]、輸入該長數位，然後輸入回應。</span><span class="sxs-lookup"><span data-stu-id="1fcee-168">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="1fcee-169">憑證授權單位</span><span class="sxs-lookup"><span data-stu-id="1fcee-169">Certificate Authority</span></span>

<span data-ttu-id="1fcee-170">確認用來頒發 Office Web Apps Server 2013 憑證的憑證頒發機構有包含在憑證撤銷清單屬性中的 HTTP 路徑。</span><span class="sxs-lookup"><span data-stu-id="1fcee-170">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="1fcee-171">如果您使用商務用 Skype Server，請將證書檔案（.crt）匯入 Skype 房間系統。</span><span class="sxs-lookup"><span data-stu-id="1fcee-171">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="1fcee-172">它很容易從 CA 伺服器的 CertEnroll 共用，或在任何加入網域的電腦上的信任根資料夾中取得。</span><span class="sxs-lookup"><span data-stu-id="1fcee-172">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="1fcee-173">證書</span><span class="sxs-lookup"><span data-stu-id="1fcee-173">Certificates</span></span>

<span data-ttu-id="1fcee-174">確認您的認證機構有憑證撤銷清單的 HTTP 路徑。</span><span class="sxs-lookup"><span data-stu-id="1fcee-174">Verify your Certificate Authority has an http path for the Certificate Revocation List.</span></span> <span data-ttu-id="1fcee-175">如果不是，請更新您的 CA 以納入其中。</span><span class="sxs-lookup"><span data-stu-id="1fcee-175">If not, update your CA to include one.</span></span>
  
<span data-ttu-id="1fcee-176">在 [系統設定\>憑證管理員] 下的 Skype 會議室系統管理員設定中安裝憑證。</span><span class="sxs-lookup"><span data-stu-id="1fcee-176">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="1fcee-177">您需要內部憑證的企業根 CA。</span><span class="sxs-lookup"><span data-stu-id="1fcee-177">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="1fcee-178">取得您所需憑證的其中一個方法是探索頒發您的憑證的 CA。</span><span class="sxs-lookup"><span data-stu-id="1fcee-178">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="1fcee-179">如果是商務用 Skype Server，請在商務用 Skype 中的電腦上\> ， \>按一下 [設定工具電話撥入會議設定]。</span><span class="sxs-lookup"><span data-stu-id="1fcee-179">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="1fcee-180">這會開啟由頒發內部憑證的 CA 保護的網頁。</span><span class="sxs-lookup"><span data-stu-id="1fcee-180">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="1fcee-181">按一下瀏覽器 [位址] 列上的 [鎖定] 圖示，以顯示安全性報告。</span><span class="sxs-lookup"><span data-stu-id="1fcee-181">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="1fcee-182">按一下 [查看憑證]，然後檢查 [CRL 發佈點] 屬性。</span><span class="sxs-lookup"><span data-stu-id="1fcee-182">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="1fcee-183">第二個 CN 參數應該是 CA 的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="1fcee-183">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="1fcee-184">現在，針對該位址\\ \< CA 伺服器名稱\>\CertEnroll. 開啟 [Windows 資源管理器]。</span><span class="sxs-lookup"><span data-stu-id="1fcee-184">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="1fcee-185">將兩個 .crl 檔案和 .crt 檔案複製到快閃記憶體磁碟機，並將它放在智慧卡的左側。</span><span class="sxs-lookup"><span data-stu-id="1fcee-185">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="1fcee-186">將 .crt 檔案匯入 [受信任的聊天室憑證授權單位] 資料夾下的 Skype 房間系統。</span><span class="sxs-lookup"><span data-stu-id="1fcee-186">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="1fcee-187">將 .crl 檔案匯入到 [中間憑證頒發機構] 資料夾底下的 Skype 聊天室系統中。</span><span class="sxs-lookup"><span data-stu-id="1fcee-187">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="1fcee-188">（您必須將 [憑證管理員] 中的 [檔案延伸] 篩選器變更為 [crl]，才能查看檔案）。</span><span class="sxs-lookup"><span data-stu-id="1fcee-188">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="1fcee-189">注意： Office Web Apps 2013 server 可能會與商務用 Skype 共用同一個 CA。</span><span class="sxs-lookup"><span data-stu-id="1fcee-189">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="1fcee-190">如果不能在會議中共用 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="1fcee-190">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="1fcee-191">如上述所述，請查看並從 CA 網路共用 CertEnroll 中取得 CRT 和 CRL 檔案。</span><span class="sxs-lookup"><span data-stu-id="1fcee-191">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="1fcee-192">網域成員資格可簡化部分作業，因為您可以將 Skype 房間系統視為 Windows 系統，而且它可以在 Active Directory 上尋找一些憑證的相關內容。</span><span class="sxs-lookup"><span data-stu-id="1fcee-192">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="1fcee-193">不過，最好是手動管理此專案。</span><span class="sxs-lookup"><span data-stu-id="1fcee-193">However, it's best to manually manage this.</span></span>
  

