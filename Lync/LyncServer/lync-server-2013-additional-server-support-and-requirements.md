---
title: Lync Server 2013：其他伺服器支援和需求
description: Lync Server 2013：其他伺服器支援和需求。
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
ms.openlocfilehash: 3af9b3489ba62b3b2dc7cf4fa16cabfe80003e1e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542329"
---
# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a><span data-ttu-id="31a50-103">Lync Server 2013 中的其他伺服器支援和需求</span><span class="sxs-lookup"><span data-stu-id="31a50-103">Additional server support and requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31a50-104">_**主題上次修改日期：** 2013-12-09_</span><span class="sxs-lookup"><span data-stu-id="31a50-104">_**Topic Last Modified:** 2013-12-09_</span></span>

<span data-ttu-id="31a50-105">除了此支援檔的其他章節所述的軟體支援之外，Lync Server 2013 還提供下列支援限制：</span><span class="sxs-lookup"><span data-stu-id="31a50-105">In addition to the software support described in the other sections of this Supportability documentation, Lync Server 2013 has the following support limitations:</span></span>

  - <span data-ttu-id="31a50-106">Lync Server 2013 支援網域名稱系統 (DNS) 和特定伺服器角色的硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="31a50-106">Lync Server 2013 supports Domain Name System (DNS) and hardware load balancing for specific server roles.</span></span> <span data-ttu-id="31a50-107">也支援對中繼伺服器使用應用程式負載平衡 (若情況允許)。</span><span class="sxs-lookup"><span data-stu-id="31a50-107">It also supports application load balancing for Mediation Servers, where appropriate.</span></span> <span data-ttu-id="31a50-108">如需各項目使用時機的詳細資訊，請參閱＜規劃＞文件。</span><span class="sxs-lookup"><span data-stu-id="31a50-108">For details about when to use each, see the Planning documentation.</span></span>

  - <span data-ttu-id="31a50-109">Lync Server 2013 使用通訊群組清單擴充通訊協定 (DLX) 來展開通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="31a50-109">Lync Server 2013 uses the Distribution List Expansion Protocol (DLX) to expand distribution lists.</span></span> <span data-ttu-id="31a50-110">此通訊協定也會指定為了取得通訊群組清單的成員資格而使用的 Web 服務方法。</span><span class="sxs-lookup"><span data-stu-id="31a50-110">This protocol also specifies the web service method that is used to get the membership of a distribution list.</span></span> <span data-ttu-id="31a50-111">Microsoft Exchange Server 支援未以靜態方式指派成員的動態群組。</span><span class="sxs-lookup"><span data-stu-id="31a50-111">Microsoft Exchange Server supports dynamic groups that do not have members statically assigned to them.</span></span> <span data-ttu-id="31a50-112">這些群組中儲存在展開群組時才會評估的查詢。</span><span class="sxs-lookup"><span data-stu-id="31a50-112">Instead, they store queries that are evaluated when the group is expanded.</span></span> <span data-ttu-id="31a50-113">DLX 不支援動態通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="31a50-113">DLX does not support dynamic distribution lists.</span></span> <span data-ttu-id="31a50-114">此 DLX 限制適用于所有的 Lync Server 版本。</span><span class="sxs-lookup"><span data-stu-id="31a50-114">This DLX limitation applies to all versions of Lync Server.</span></span>

  - <span data-ttu-id="31a50-115">[啟用使用者精靈] 不支援自動將非英文字元轉換成符合 SIP 標準的 URI，因此您必須手動修改 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="31a50-115">The Enable User Wizard does not support automatic conversion of non-English characters to a SIP-compliant URI, so you must modify the SIP address manually.</span></span>

  - <span data-ttu-id="31a50-116">針對執行防毒軟體的伺服器，請參閱 [Lync Server 2013 的防病毒掃描排除](lync-server-2013-antivirus-scanning-exclusions.md) ，以取得建議的病毒排除和其他安全性相關建議。</span><span class="sxs-lookup"><span data-stu-id="31a50-116">For servers running antivirus software, refer to [Antivirus scanning exclusions for Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) for suggested virus exclusions and other security related recommendations.</span></span>

  - <span data-ttu-id="31a50-117">如果您有使用 IPsec，我們建議您針對音訊與視訊流量所使用的連接埠範圍停用 IPsec。</span><span class="sxs-lookup"><span data-stu-id="31a50-117">If you use IPsec, we recommend disabling IPsec over the port ranges used for audio and video traffic.</span></span> <span data-ttu-id="31a50-118">如需詳細資訊，請參閱規劃檔中的 [IPsec 的 Lync Server 2013](lync-server-2013-ipsec-exceptions.md) 中的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="31a50-118">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="31a50-119">如果您的組織使用的是服務品質 (QoS) 基礎結構，則媒體子系統將會設計成配合此現有基礎結構運作。</span><span class="sxs-lookup"><span data-stu-id="31a50-119">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span> <span data-ttu-id="31a50-120">如需有關執行 QoS 的詳細資訊，請參閱 Operations 檔中的 [管理 Lync Server 2013 中的服務品質 (QoS) ](lync-server-2013-managing-quality-of-service-qos.md) 。</span><span class="sxs-lookup"><span data-stu-id="31a50-120">For details about implementing QoS, see [Managing Quality of Service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="31a50-121">支援使用作業系統防火牆。</span><span class="sxs-lookup"><span data-stu-id="31a50-121">Use of the operating system firewall is supported.</span></span> <span data-ttu-id="31a50-122">Lync Server 2013 管理作業系統防火牆的防火牆例外狀況，但 Microsoft SQL Server 資料庫軟體除外。</span><span class="sxs-lookup"><span data-stu-id="31a50-122">Lync Server 2013 manages the firewall exceptions for the operating system firewall, except for Microsoft SQL Server database software.</span></span> <span data-ttu-id="31a50-123">如需 SQL Server 防火牆需求的詳細資訊，請參閱 SQL Server 文件。</span><span class="sxs-lookup"><span data-stu-id="31a50-123">For details about SQL Server firewall requirements, see the SQL Server documentation.</span></span>

  - <span data-ttu-id="31a50-124">用來實作外部使用者存取支援的外部介面必須位於個別子網路，而非\*\* 與內部介面位於相同網路。</span><span class="sxs-lookup"><span data-stu-id="31a50-124">The external interfaces used to implement support for external user access must be on a separate subnet, *not* on the same network as the internal interfaces.</span></span>

  - <span data-ttu-id="31a50-125">Lync Server 2013 的 XMPP 功能會經過測試，並受 Microsoft 支援，以進行與 Google 交談的立即訊息同盟。</span><span class="sxs-lookup"><span data-stu-id="31a50-125">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="31a50-126">對於任何其他 XMPP 系統，請聯繫協力廠商廠商，以確認其支援與 Lync Server 2013 的同盟，以及任何部署或疑難排解建議。</span><span class="sxs-lookup"><span data-stu-id="31a50-126">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>

  - <span data-ttu-id="31a50-127">使用 Lync Server 2013 累計更新的發行：7月2013，Lync Server 2013 現在支援雙因素驗證。</span><span class="sxs-lookup"><span data-stu-id="31a50-127">With the release of Lync Server 2013 Cumulative Updates: July 2013, Lync Server 2013 now supports two-factor authentication.</span></span> <span data-ttu-id="31a50-128">如需詳細資訊，請參閱 [Lync Server 2013 中的兩要素驗證](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="31a50-128">For more information, see [Two-factor authentication in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span></span>

  - <span data-ttu-id="31a50-129">大多數內部伺服器都需要以「 **開啟驗證** (」 OAuth) 定義的憑證類型。</span><span class="sxs-lookup"><span data-stu-id="31a50-129">Most internal servers require a certificate type defined as **Open Authentication** (OAuth).</span></span> <span data-ttu-id="31a50-130">在 [Lync Server 部署嚮導] 的 [ **要求、安裝與指派憑證** ] 階段中，需要要求並指派 OAuth 憑證。</span><span class="sxs-lookup"><span data-stu-id="31a50-130">You are required to request and assign an OAuth certificate during the **Request, Install and Assign Certificates** phase of the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="31a50-131">OAuth 憑證金鑰的大小下限為1024位。</span><span class="sxs-lookup"><span data-stu-id="31a50-131">The minimum size for an OAuth certificate key is 1024 bits.</span></span> <span data-ttu-id="31a50-132">如果您要求密碼長度小於2048位的憑證，則會顯示警告。</span><span class="sxs-lookup"><span data-stu-id="31a50-132">A warning may be displayed if you request a certificate with a key length less than 2048 bits in length.</span></span> <span data-ttu-id="31a50-133">為了避免發生潛在問題（而不是警告的金鑰長度為2048），強烈建議您在 OAuth 憑證中，永遠使用金鑰長度2048。</span><span class="sxs-lookup"><span data-stu-id="31a50-133">To avoid potential problems in the event that a key length of 2048 is enforced instead of warned, it is strongly recommended to always use a key length of 2048 for OAuth certificates.</span></span>

  - <span data-ttu-id="31a50-134">Lync Server 2013 和 Microsoft Exchange Server 2010 Service Pack 1 (SP1) 運作支援聯邦資訊處理標準 (FIPS) 140-2 演算法（如果 Windows Server 2008 R2 作業系統設定為使用 FIPS 140-2 演算法進行系統加密）。</span><span class="sxs-lookup"><span data-stu-id="31a50-134">Lync Server 2013 and Microsoft Exchange Server 2010 Service Pack 1 (SP1) operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server 2008 R2 operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="31a50-135">若要實施 FIPS 支援，您必須設定每台執行 Lync Server 2013 的伺服器以支援它。</span><span class="sxs-lookup"><span data-stu-id="31a50-135">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="31a50-136">如需 FIPS 相容的演算法及如何實施 FIPS 支援的詳細資訊，請參閱 Microsoft 知識庫文章811833：在 Windows XP 和更新版本的 Windows 中，使用 FIPS 相容演算法進行加密、雜湊和簽署安全性設定 [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833) 。</span><span class="sxs-lookup"><span data-stu-id="31a50-136">For details about FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, "System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing security setting in Windows XP and in later versions of Windows at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="31a50-137">如需 Exchange 2010 中的 FIPS 140-2 支援和限制的詳細資訊，請參閱《 Exchange 2010 SP1 及支援 FIPS 相容的演算法》 [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335) 。</span><span class="sxs-lookup"><span data-stu-id="31a50-137">For details about FIPS 140-2 support and limitations in Exchange 2010, see "Exchange 2010 SP1 and Support for FIPS Compliant Algorithms" at [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

<span data-ttu-id="31a50-138">Lync Server 2013 需要在部署之前或之後，在特定元件上安裝其他軟體。</span><span class="sxs-lookup"><span data-stu-id="31a50-138">Lync Server 2013 requires the installation of other software on specific components prior to or during deployment.</span></span> <span data-ttu-id="31a50-139">這包括在安裝 Lync Server 2013 期間自動安裝的作業系統、可下載軟體和軟體中所提供的軟體。</span><span class="sxs-lookup"><span data-stu-id="31a50-139">This includes software that is available with the operating system, downloadable software, and software that is automatically installed during installation of Lync Server 2013.</span></span> <span data-ttu-id="31a50-140">以下列出其他可能需要的軟體：</span><span class="sxs-lookup"><span data-stu-id="31a50-140">Following is a list of additional software that can be required:</span></span>

  - <span data-ttu-id="31a50-141">Windows Update</span><span class="sxs-lookup"><span data-stu-id="31a50-141">Windows Update</span></span>

  - <span data-ttu-id="31a50-142">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="31a50-142">Windows Identity Foundation</span></span>

  - <span data-ttu-id="31a50-143">Microsoft .NET 4.5 Framework</span><span class="sxs-lookup"><span data-stu-id="31a50-143">Microsoft .NET 4.5 Framework</span></span>

  - <span data-ttu-id="31a50-144">Microsoft Visual c + + 2012 可轉散發元件</span><span class="sxs-lookup"><span data-stu-id="31a50-144">Microsoft Visual C++ 2012 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="31a50-145">當您安裝 Lync Server 2013 時，會自動安裝 Microsoft Visual c + + 2012 可轉散發元件。</span><span class="sxs-lookup"><span data-stu-id="31a50-145">Microsoft Visual C++ 2012 Redistributable is automatically installed when you install Lync Server 2013.</span></span> <span data-ttu-id="31a50-146">您不應該安裝和使用任何其他版本。</span><span class="sxs-lookup"><span data-stu-id="31a50-146">You should not install and use any other version.</span></span>

    
    </div>

  - <span data-ttu-id="31a50-147">URL Rewrite Module Version 2.0 可轉散發套件</span><span class="sxs-lookup"><span data-stu-id="31a50-147">URL Rewrite Module version 2.0 Redistributable</span></span>

  - <span data-ttu-id="31a50-148">Windows Media Format Runtime</span><span class="sxs-lookup"><span data-stu-id="31a50-148">Windows Media Format Runtime</span></span>

  - <span data-ttu-id="31a50-149">Windows PowerShell 版本3。0</span><span class="sxs-lookup"><span data-stu-id="31a50-149">Windows PowerShell version 3.0</span></span>

  - <span data-ttu-id="31a50-150">Microsoft Silverlight 4 瀏覽器外掛程式 (Lync Server 控制台需要 Silverlight 4.0.50524.0 或最新的版本)</span><span class="sxs-lookup"><span data-stu-id="31a50-150">Microsoft Silverlight 4 browser plug-in (Silverlight 4.0.50524.0 or the latest version for Lync Server Control Panel)</span></span>

  - <span data-ttu-id="31a50-151">Active Directory 網域服務工具</span><span class="sxs-lookup"><span data-stu-id="31a50-151">Active Directory Domain Services tools</span></span>

<span data-ttu-id="31a50-152">其中有些軟體需求僅適用於特定伺服器角色或元件。</span><span class="sxs-lookup"><span data-stu-id="31a50-152">Some of these software requirements only apply to specific server roles or components.</span></span> <span data-ttu-id="31a50-153">如需這些軟體需求的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 其他軟體需求](lync-server-2013-additional-software-requirements.md) 。</span><span class="sxs-lookup"><span data-stu-id="31a50-153">For details about these software requirements, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

