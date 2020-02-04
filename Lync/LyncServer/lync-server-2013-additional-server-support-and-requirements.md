---
title: Lync Server 2013：其他伺服器支援和需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f111b80bc88b632ff1020f45e899f220edeb7d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a><span data-ttu-id="76920-102">Lync Server 2013 中的其他伺服器支援和需求</span><span class="sxs-lookup"><span data-stu-id="76920-102">Additional server support and requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76920-103">_**主題上次修改日期：** 2013-12-09_</span><span class="sxs-lookup"><span data-stu-id="76920-103">_**Topic Last Modified:** 2013-12-09_</span></span>

<span data-ttu-id="76920-104">除了本支援檔的其他章節所述的軟體支援之外，Lync Server 2013 還有下列支援限制：</span><span class="sxs-lookup"><span data-stu-id="76920-104">In addition to the software support described in the other sections of this Supportability documentation, Lync Server 2013 has the following support limitations:</span></span>

  - <span data-ttu-id="76920-105">Lync Server 2013 支援針對特定伺服器角色的網域名稱系統（DNS）和硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="76920-105">Lync Server 2013 supports Domain Name System (DNS) and hardware load balancing for specific server roles.</span></span> <span data-ttu-id="76920-106">它也支援針對轉送伺服器的應用程式負載平衡（在適當的位置）。</span><span class="sxs-lookup"><span data-stu-id="76920-106">It also supports application load balancing for Mediation Servers, where appropriate.</span></span> <span data-ttu-id="76920-107">如需每個使用時間的詳細資訊，請參閱規劃檔。</span><span class="sxs-lookup"><span data-stu-id="76920-107">For details about when to use each, see the Planning documentation.</span></span>

  - <span data-ttu-id="76920-108">Lync Server 2013 使用通訊群組清單展開通訊協定（DLX）來展開通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="76920-108">Lync Server 2013 uses the Distribution List Expansion Protocol (DLX) to expand distribution lists.</span></span> <span data-ttu-id="76920-109">這個通訊協定也會指定用來取得通訊群組清單成員資格的 web 服務方法。</span><span class="sxs-lookup"><span data-stu-id="76920-109">This protocol also specifies the web service method that is used to get the membership of a distribution list.</span></span> <span data-ttu-id="76920-110">Microsoft Exchange Server 支援沒有靜態指派成員的動態群組。</span><span class="sxs-lookup"><span data-stu-id="76920-110">Microsoft Exchange Server supports dynamic groups that do not have members statically assigned to them.</span></span> <span data-ttu-id="76920-111">相反地，它們會儲存在展開群組時評估的查詢。</span><span class="sxs-lookup"><span data-stu-id="76920-111">Instead, they store queries that are evaluated when the group is expanded.</span></span> <span data-ttu-id="76920-112">DLX 不支援動態通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="76920-112">DLX does not support dynamic distribution lists.</span></span> <span data-ttu-id="76920-113">此 DLX 限制適用于所有版本的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="76920-113">This DLX limitation applies to all versions of Lync Server.</span></span>

  - <span data-ttu-id="76920-114">[啟用使用者] 嚮導不支援將非英文字元自動轉換成與 SIP 相容的 URI，因此您必須手動修改 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="76920-114">The Enable User Wizard does not support automatic conversion of non-English characters to a SIP-compliant URI, so you must modify the SIP address manually.</span></span>

  - <span data-ttu-id="76920-115">針對執行防毒軟體的伺服器，請參閱[Lync Server 2013 的防病毒掃描排除](lync-server-2013-antivirus-scanning-exclusions.md)程式，以取得建議的病毒排除及其他安全性相關建議。</span><span class="sxs-lookup"><span data-stu-id="76920-115">For servers running antivirus software, refer to [Antivirus scanning exclusions for Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) for suggested virus exclusions and other security related recommendations.</span></span>

  - <span data-ttu-id="76920-116">如果您使用的是 IPsec，我們建議您在用於音訊與視頻流量的埠範圍停用 IPsec。</span><span class="sxs-lookup"><span data-stu-id="76920-116">If you use IPsec, we recommend disabling IPsec over the port ranges used for audio and video traffic.</span></span> <span data-ttu-id="76920-117">如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的 IPsec 例外](lync-server-2013-ipsec-exceptions.md)狀況。</span><span class="sxs-lookup"><span data-stu-id="76920-117">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="76920-118">如果您的組織使用的是服務品質（QoS）基礎結構，媒體子系統就是設計來在這個現有的基礎結構中運作。</span><span class="sxs-lookup"><span data-stu-id="76920-118">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span> <span data-ttu-id="76920-119">如需有關實施 QoS 的詳細資料，請參閱在作業檔中[管理 Lync Server 2013 中的服務品質（QoS）](lync-server-2013-managing-quality-of-service-qos.md) 。</span><span class="sxs-lookup"><span data-stu-id="76920-119">For details about implementing QoS, see [Managing Quality of Service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="76920-120">支援使用作業系統防火牆。</span><span class="sxs-lookup"><span data-stu-id="76920-120">Use of the operating system firewall is supported.</span></span> <span data-ttu-id="76920-121">Lync Server 2013 可管理作業系統防火牆的防火牆例外狀況（Microsoft SQL Server 資料庫軟體除外）。</span><span class="sxs-lookup"><span data-stu-id="76920-121">Lync Server 2013 manages the firewall exceptions for the operating system firewall, except for Microsoft SQL Server database software.</span></span> <span data-ttu-id="76920-122">如需 SQL Server 防火牆需求的詳細資訊，請參閱 SQL Server 檔。</span><span class="sxs-lookup"><span data-stu-id="76920-122">For details about SQL Server firewall requirements, see the SQL Server documentation.</span></span>

  - <span data-ttu-id="76920-123">用來實現外部使用者存取支援的外部介面必須位於個別的子網上，*而不*是與內部介面相同的網路上。</span><span class="sxs-lookup"><span data-stu-id="76920-123">The external interfaces used to implement support for external user access must be on a separate subnet, *not* on the same network as the internal interfaces.</span></span>

  - <span data-ttu-id="76920-124">Lync Server 2013 的 XMPP 功能是由 Microsoft 針對使用 Google 交談的立即訊息同盟進行測試和支援。</span><span class="sxs-lookup"><span data-stu-id="76920-124">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="76920-125">針對任何其他 XMPP 系統，請與協力廠商廠商聯繫，確認他們支援 Lync Server 2013 的同盟，以及任何部署或疑難排解建議。</span><span class="sxs-lookup"><span data-stu-id="76920-125">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>

  - <span data-ttu-id="76920-126">在發行 Lync Server 2013 累計更新：2013年7月，Lync Server 2013 現在支援雙因素驗證。</span><span class="sxs-lookup"><span data-stu-id="76920-126">With the release of Lync Server 2013 Cumulative Updates: July 2013, Lync Server 2013 now supports two-factor authentication.</span></span> <span data-ttu-id="76920-127">如需詳細資訊，請參閱[Lync Server 2013 中的雙因素驗證](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="76920-127">For more information, see [Two-factor authentication in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span></span>

  - <span data-ttu-id="76920-128">大多數內部伺服器都需要定義為「**開啟驗證**（OAuth）」的憑證類型。</span><span class="sxs-lookup"><span data-stu-id="76920-128">Most internal servers require a certificate type defined as **Open Authentication** (OAuth).</span></span> <span data-ttu-id="76920-129">您必須在 [Lync Server 部署嚮導] 的 [**要求中安裝並指派憑證**] 階段，要求並指派 OAuth 憑證。</span><span class="sxs-lookup"><span data-stu-id="76920-129">You are required to request and assign an OAuth certificate during the **Request, Install and Assign Certificates** phase of the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="76920-130">OAuth 憑證金鑰的最小大小為1024位。</span><span class="sxs-lookup"><span data-stu-id="76920-130">The minimum size for an OAuth certificate key is 1024 bits.</span></span> <span data-ttu-id="76920-131">如果您要求密碼長度少於2048位的憑證，可能會顯示警告。</span><span class="sxs-lookup"><span data-stu-id="76920-131">A warning may be displayed if you request a certificate with a key length less than 2048 bits in length.</span></span> <span data-ttu-id="76920-132">若要避免在強制執行金鑰長度為2048而不是警告的情況下發生問題，強烈建議您在 OAuth 憑證中，永遠使用金鑰長度2048。</span><span class="sxs-lookup"><span data-stu-id="76920-132">To avoid potential problems in the event that a key length of 2048 is enforced instead of warned, it is strongly recommended to always use a key length of 2048 for OAuth certificates.</span></span>

  - <span data-ttu-id="76920-133">Lync Server 2013 和 Microsoft Exchange Server 2010 Service Pack 1 （SP1）的運作支援聯邦資訊處理標準（FIPS）140-2 演算法（如果 Windows Server 2008 R2 作業系統已設定為使用 FIPS 140-2 演算法）系統加密。</span><span class="sxs-lookup"><span data-stu-id="76920-133">Lync Server 2013 and Microsoft Exchange Server 2010 Service Pack 1 (SP1) operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server 2008 R2 operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="76920-134">若要實現 FIPS 支援，您必須設定執行 Lync Server 2013 的每個伺服器以支援它。</span><span class="sxs-lookup"><span data-stu-id="76920-134">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="76920-135">如需與 FIPS 相容的演算法以及如何實現 FIPS 支援的詳細資料，請參閱 Microsoft 知識庫文章811833，「系統加密：使用 FIPS 相容的演算法來加密、雜湊及簽署安全設定（在 Windows XP 中以及更新[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)版本的 windows 中）。</span><span class="sxs-lookup"><span data-stu-id="76920-135">For details about FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, "System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing security setting in Windows XP and in later versions of Windows at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="76920-136">如需有關 FIPS 140-2 支援的詳細資訊，以及 Exchange 2010 中的限制，請參閱「Exchange 2010 SP1 和支援[http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)的 Fips 相容性演算法」。</span><span class="sxs-lookup"><span data-stu-id="76920-136">For details about FIPS 140-2 support and limitations in Exchange 2010, see "Exchange 2010 SP1 and Support for FIPS Compliant Algorithms" at [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

<span data-ttu-id="76920-137">Lync Server 2013 需要在部署之前或期間，在特定元件上安裝其他軟體。</span><span class="sxs-lookup"><span data-stu-id="76920-137">Lync Server 2013 requires the installation of other software on specific components prior to or during deployment.</span></span> <span data-ttu-id="76920-138">這包括在安裝 Lync Server 2013 期間自動安裝的作業系統、可下載軟體和軟體所提供的軟體。</span><span class="sxs-lookup"><span data-stu-id="76920-138">This includes software that is available with the operating system, downloadable software, and software that is automatically installed during installation of Lync Server 2013.</span></span> <span data-ttu-id="76920-139">以下是可能需要的其他軟體清單：</span><span class="sxs-lookup"><span data-stu-id="76920-139">Following is a list of additional software that can be required:</span></span>

  - <span data-ttu-id="76920-140">Windows Update</span><span class="sxs-lookup"><span data-stu-id="76920-140">Windows Update</span></span>

  - <span data-ttu-id="76920-141">Windows 身分識別基礎</span><span class="sxs-lookup"><span data-stu-id="76920-141">Windows Identity Foundation</span></span>

  - <span data-ttu-id="76920-142">Microsoft .NET 4.5 Framework</span><span class="sxs-lookup"><span data-stu-id="76920-142">Microsoft .NET 4.5 Framework</span></span>

  - <span data-ttu-id="76920-143">Microsoft Visual c + + 2012 可轉散發元件</span><span class="sxs-lookup"><span data-stu-id="76920-143">Microsoft Visual C++ 2012 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="76920-144">安裝 Lync Server 2013 時，系統會自動安裝 Microsoft Visual c + + 2012 可再發行的功能。</span><span class="sxs-lookup"><span data-stu-id="76920-144">Microsoft Visual C++ 2012 Redistributable is automatically installed when you install Lync Server 2013.</span></span> <span data-ttu-id="76920-145">您不應該安裝並使用任何其他版本。</span><span class="sxs-lookup"><span data-stu-id="76920-145">You should not install and use any other version.</span></span>

    
    </div>

  - <span data-ttu-id="76920-146">URL 重新寫入模組版本2.0 可再發行</span><span class="sxs-lookup"><span data-stu-id="76920-146">URL Rewrite Module version 2.0 Redistributable</span></span>

  - <span data-ttu-id="76920-147">Windows Media 格式執行時間</span><span class="sxs-lookup"><span data-stu-id="76920-147">Windows Media Format Runtime</span></span>

  - <span data-ttu-id="76920-148">Windows PowerShell 版本3。0</span><span class="sxs-lookup"><span data-stu-id="76920-148">Windows PowerShell version 3.0</span></span>

  - <span data-ttu-id="76920-149">Microsoft Silverlight 4 瀏覽器外掛程式（Silverlight 4.0.50524.0 或 Lync Server [控制台] 的最新版本）</span><span class="sxs-lookup"><span data-stu-id="76920-149">Microsoft Silverlight 4 browser plug-in (Silverlight 4.0.50524.0 or the latest version for Lync Server Control Panel)</span></span>

  - <span data-ttu-id="76920-150">Active Directory 網域服務工具</span><span class="sxs-lookup"><span data-stu-id="76920-150">Active Directory Domain Services tools</span></span>

<span data-ttu-id="76920-151">某些軟體需求只適用于特定伺服器角色或元件。</span><span class="sxs-lookup"><span data-stu-id="76920-151">Some of these software requirements only apply to specific server roles or components.</span></span> <span data-ttu-id="76920-152">如需這些軟體需求的詳細資訊，請參閱規劃檔中[Lync Server 2013 的其他軟體需求](lync-server-2013-additional-software-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="76920-152">For details about these software requirements, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

