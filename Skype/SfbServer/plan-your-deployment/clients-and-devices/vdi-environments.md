---
title: 規劃 VDI 環境中的商務用 Skype
author: lanachin
ms.author: v-lanac
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: 本主題討論在連線至遠端虛擬桌面時, 使用商務用 Skype 的規劃考慮。
ms.openlocfilehash: c6bf1cea2a18920231ea4d347b8b0471cfebbba3
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "36193947"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a><span data-ttu-id="a8495-103">規劃 VDI 環境中的商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="a8495-103">Plan for Skype for Business in VDI environments</span></span>
 
<span data-ttu-id="a8495-104">本主題討論在連線至遠端虛擬桌面時, 使用商務用 Skype 的規劃考慮。</span><span class="sxs-lookup"><span data-stu-id="a8495-104">This topic discusses planning considerations for using Skype for Business while connecting to a remote virtual desktop.</span></span> 
  
<span data-ttu-id="a8495-105">虛擬桌面基礎結構 (VDI) 環境是在安全性與合規性問題特別敏感的一些組織中使用。</span><span class="sxs-lookup"><span data-stu-id="a8495-105">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="a8495-106">他們的使用者使用遠端桌面服務或類似的遠端連線, 在虛擬桌面完成其工作 (含所有桌面應用程式和檔案)。</span><span class="sxs-lookup"><span data-stu-id="a8495-106">Their users do their work on a virtual desktop with all their desktop applications and files using Remote Desktop Services or a similar remote connection.</span></span> <span data-ttu-id="a8495-107">在連線時使用商務用 Skype, 在連線時, 在用戶端上的音訊和視頻處理需要大量載入, 才能在虛擬機器上託管。</span><span class="sxs-lookup"><span data-stu-id="a8495-107">Using Skype for Business with full audio and video on a connection like that requires heavy loads of audio and video processing on the client homed on a virtual desktop.</span></span> <span data-ttu-id="a8495-108">您可以使用其他 VDI 外掛程式軟體, 將該處理減輕到使用者的本機電腦, 並減少虛擬桌面機的負載。</span><span class="sxs-lookup"><span data-stu-id="a8495-108">Additional VDI plug-in software is available that offloads that processing to the end user's local machine, and reduces the load on the virtual desktop.</span></span>
  
<span data-ttu-id="a8495-109">有三個解決方案可供 Microsoft、Citrix 或 VMWare 提供的 VDI 外掛程式元件使用。</span><span class="sxs-lookup"><span data-stu-id="a8495-109">There are three solutions available for the VDI plug-in component, offered by Microsoft, Citrix, or VMWare.</span></span> <span data-ttu-id="a8495-110">針對新的部署, Microsoft 建議使用 Citrix HDX 即時優化套件方案或 VMWare 地平線虛擬化套件。</span><span class="sxs-lookup"><span data-stu-id="a8495-110">For new deployments, Microsoft recommends using either the Citrix HDX RealTime Optimization Pack solution or the VMWare Horizon Virtualization Pack.</span></span> <span data-ttu-id="a8495-111">原始的 Lync VDI 外掛程式在其整個生命週期的剩餘部分中仍然受到支援。</span><span class="sxs-lookup"><span data-stu-id="a8495-111">The original Lync VDI Plug-in is still supported for the remainder of its lifecycle.</span></span>
  
- <span data-ttu-id="a8495-112">Lync **VDI 外掛程式**是針對 lync 2013 開發的, 且與在虛擬機器上執行的 lync 2013 或商務用 Skype 2015 用戶端相容。</span><span class="sxs-lookup"><span data-stu-id="a8495-112">The **Lync VDI plug-in** was developed for Lync 2013 and is compatible with either the Lync 2013 or Skype for Business 2015 client running on a virtual desktop.</span></span> <span data-ttu-id="a8495-113">它是安裝在本機電腦上的獨立應用程式, 可讓您在虛擬機器上使用本機音訊和視頻裝置搭配用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="a8495-113">It's a stand-alone application that installs on the local computer and allows the use of local audio and video devices with a client on a virtual desktop.</span></span> <span data-ttu-id="a8495-114">外掛程式不需要在本機電腦或瘦用戶端上安裝商務用 Skype 用戶端, 必須執行 Windows 7、Windows 8 或 Windows Server 2008 作業系統。</span><span class="sxs-lookup"><span data-stu-id="a8495-114">The plug-in does not require a Skype for Business client to be installed on the local computer or thin client, which must run Windows 7, Windows 8, or Windows Server 2008 operating systems.</span></span> <span data-ttu-id="a8495-115">(使用這些作業系統並受 Microsoft 支援的瘦用戶端裝置包括: Dell Wyse Z90D7、戴爾 Wyse R90L7、Dell Wyse X90m7、HP t610 和 HP t5740e。)此外掛程式仍受到支援, 但將來沒有規劃任何更新。</span><span class="sxs-lookup"><span data-stu-id="a8495-115">(Thin client devices using these operating systems and supported by Microsoft include: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 and HP t5740e.) This plug-in is still supported, but no future updates are planned.</span></span> <span data-ttu-id="a8495-116">對於基於 Citrix 的虛擬環境, 建議使用 Citrix 即時優化套件。</span><span class="sxs-lookup"><span data-stu-id="a8495-116">For Citrix-based virtual environments, the Citrix RealTime Optimization Pack is recommended.</span></span>
    
- <span data-ttu-id="a8495-117">**Citrix 即時優化套件**是在 lync VDI 外掛程式上建立, 且可與 Lync 2013 或虛擬機器上的商務用 Skype 2016 用戶端搭配使用。</span><span class="sxs-lookup"><span data-stu-id="a8495-117">The **Citrix RealTime Optimization Pack** builds on the Lync VDI plug-in and works with Lync 2013 or Skype for Business 2016 clients on a virtual desktop.</span></span> <span data-ttu-id="a8495-118">它由 Citrix 與 Microsoft 共同開發, 可在原始的 VDI 外掛程式上改善。</span><span class="sxs-lookup"><span data-stu-id="a8495-118">It was co-developed by Citrix and Microsoft to improve upon the original VDI Plug-in.</span></span> <span data-ttu-id="a8495-119">它可以安裝在裝有 Windows 和非 Windows 作業系統 (包括 Windows 10、Mac 和 Linux) 的用戶端。</span><span class="sxs-lookup"><span data-stu-id="a8495-119">It can be installed on clients with Windows and non-Windows operating systems (including Windows 10, Mac and Linux).</span></span> <span data-ttu-id="a8495-120">它包含兩個元件: 即時連接器 (安裝在虛擬桌面) 和即時媒體引擎 (在最終使用者的本機電腦上安裝)。</span><span class="sxs-lookup"><span data-stu-id="a8495-120">It consists of two components: the RealTime Connector (which is installed on the virtual desktop) and the RealTime Media Engine (which is installed on the end user's local machine).</span></span> <span data-ttu-id="a8495-121">這兩個元件可讓使用者的本機電腦使用在虛擬機器上執行的商務用 Skype 用戶端, 並將 A/V 處理移至本機電腦。</span><span class="sxs-lookup"><span data-stu-id="a8495-121">These two components allow the user's local computer to use the Skype for Business client running on the virtual desktop with the A/V processing moved to the local computer.</span></span> <span data-ttu-id="a8495-122">針對基於 Citrix 的虛擬桌面環境, 我們建議使用 Citrix 即時優化套件, 並規劃進一步的支援。</span><span class="sxs-lookup"><span data-stu-id="a8495-122">For Citrix-based virtual desktop environments, the Citrix RealTime Optimization Pack is recommended, and further support is planned.</span></span>
    
- <span data-ttu-id="a8495-123">商務用 Skype 的**VMWare 地平線虛擬化套件**是與 VMWare 共同作業, 可讓您在虛擬桌面中傳送商務用 skype, 同時提供絕佳的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="a8495-123">The **VMWare Horizon Virtualization Pack** for Skype for Business, developed in collaboration with VMWare, allows you to deliver Skype for Business in a virtual desktop while delivering a great user experience.</span></span> <span data-ttu-id="a8495-124">此方案的運作方式是, 利用用戶端的媒體引擎來建立優化的解決方案, 並讓用戶端端點提供媒體卸載功能以進行音訊與視頻通話。</span><span class="sxs-lookup"><span data-stu-id="a8495-124">The solution works by leveraging a media engine at the client to create an optimized solution, with the client endpoint providing media offload capabilities for audio and video calls.</span></span> <span data-ttu-id="a8495-125">這個解決方案可以在一對一共同作業的端點之間直接傳送音訊及視頻, 或將它移到多方會議通話或會議的中央 Multipoint 控制單元 (MCU)。</span><span class="sxs-lookup"><span data-stu-id="a8495-125">This solution that can deliver audio and video either directly between endpoints for one-on-one collaboration, or offload it to a central Multipoint Control Unit (MCU) for multiparty conference calls or meetings.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a8495-126">Citrix HDX 即時優化套件或 VMWare 地平線虛擬化套件不支援商務用 Skype 基本用戶端。</span><span class="sxs-lookup"><span data-stu-id="a8495-126">The Skype for Business Basic clients are not supported with the Citrix HDX RealTime Optimization Pack or the VMWare Horizon Virtualization Pack.</span></span> 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a><span data-ttu-id="a8495-127">Citrix HDX 即時優化套件</span><span class="sxs-lookup"><span data-stu-id="a8495-127">Citrix HDX RealTime Optimization Pack</span></span>
<span data-ttu-id="a8495-128"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="a8495-128"></span></span>

<span data-ttu-id="a8495-129">Citrix 的 VDI 環境外掛程式 (XenApp 和 XenDesktop) 與 Lync 2013 和商務用 Skype 2015 和 2016 (使用任何按一下以執行安裝程式的完整用戶端, 或在已安裝在虛擬機器上的 MSI 安裝程式2017之後發行) 用戶端桌面.</span><span class="sxs-lookup"><span data-stu-id="a8495-129">Citrix's VDI environment plugin (a feature of XenApp and XenDesktop) is compatible with Lync 2013 and Skype for Business 2015 and 2016 (Full clients using any click to run installer, or MSI installers released after January 2017 PU) clients installed on a virtual desktop.</span></span> <span data-ttu-id="a8495-130">它的整體運作方式是以 Microsoft Lync VDI 外掛程式為基礎, 但在各種用戶端作業系統 (包括 Windows 10、Macintosh 及 Linux) 上都能運作。</span><span class="sxs-lookup"><span data-stu-id="a8495-130">Its overall functioning is based on the Microsoft Lync VDI plug-in, but works on a wider variety of client operating systems, including Windows 10, Macintosh, and Linux.</span></span>
  
<span data-ttu-id="a8495-131">在[提供 Microsoft 商務用 Skype XenApp 和 XenDesktop 使用者](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)的 Citrix 網站上, 可以找到完整的功能清單及支援的技術。</span><span class="sxs-lookup"><span data-stu-id="a8495-131">A full list of features and supported technologies can be found on the Citrix website at [Delivering Microsoft Skype for Business to XenApp and XenDesktop Users](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).</span></span>
  
<span data-ttu-id="a8495-132">如需詳細資訊, 請參閱下列連結:</span><span class="sxs-lookup"><span data-stu-id="a8495-132">Review the following links for more information:</span></span>
  
- <span data-ttu-id="a8495-133">Citrix [HDX 即時優化套件 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)</span><span class="sxs-lookup"><span data-stu-id="a8495-133">Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)</span></span>
    
- [<span data-ttu-id="a8495-134">技術概述</span><span class="sxs-lookup"><span data-stu-id="a8495-134">Technical Overview</span></span>](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [<span data-ttu-id="a8495-135">CTX200279 商務用 Skype 功能支援</span><span class="sxs-lookup"><span data-stu-id="a8495-135">CTX200279 Skype for Business Feature Support</span></span>](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a><span data-ttu-id="a8495-136">VMWare 地平線虛擬化套件</span><span class="sxs-lookup"><span data-stu-id="a8495-136">VMWare Horizon Virtualization Pack</span></span>
<span data-ttu-id="a8495-137"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="a8495-137"></span></span>

<span data-ttu-id="a8495-138">VMWare 的 VDI 環境解決方案與在虛擬機器上安裝的商務用 Skype 2015 和2016完整用戶端相容。</span><span class="sxs-lookup"><span data-stu-id="a8495-138">VMWare's VDI environment solution is compatible with Skype for Business 2015 and 2016 Full clients installed on a virtual desktop.</span></span> <span data-ttu-id="a8495-139">它的整體運作方式是以 Microsoft Lync VDI 外掛程式為基礎, 但在各種用戶端作業系統 (包括 Windows 10、Macintosh 及 Linux) 上都能運作。</span><span class="sxs-lookup"><span data-stu-id="a8495-139">Its overall functioning is based on the Microsoft Lync VDI plug-in, but works on a wider variety of client operating systems, including Windows 10, Macintosh, and Linux.</span></span> 
  
<span data-ttu-id="a8495-140">您可以在 VMWare 網站上的下列連結中找到完整的功能和支援的技術討論:</span><span class="sxs-lookup"><span data-stu-id="a8495-140">A full discussion of features and supported technologies can be found on the VMWare website at the following links:</span></span>
  
- [<span data-ttu-id="a8495-141">VMware 7.4 的新功能水準 4.7 &amp;</span><span class="sxs-lookup"><span data-stu-id="a8495-141">What's New in VMware Horizon 7.4 &amp; Horizon Client 4.7</span></span>](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [<span data-ttu-id="a8495-142">商務用 Skype 的地平線虛擬化套件</span><span class="sxs-lookup"><span data-stu-id="a8495-142">Horizon Virtualization Pack for Skype for Business</span></span>](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [<span data-ttu-id="a8495-143">使用 VMWare 的 Microsoft 商務用 Skype 地平線</span><span class="sxs-lookup"><span data-stu-id="a8495-143">Microsoft Skype for Business With VMWare Horizon</span></span>](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a><span data-ttu-id="a8495-144">Microsoft 的 Lync VDI 外掛程式</span><span class="sxs-lookup"><span data-stu-id="a8495-144">Microsoft's Lync VDI plug-in</span></span>
<span data-ttu-id="a8495-145"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="a8495-145"></span></span>

<span data-ttu-id="a8495-146">透過 Microsoft Lync VDI 外掛程式解決方案, 使用者必須在 Windows 電腦或瘦用戶端, 且已安裝 Microsoft 的 Lync VDI 外掛程式來處理來自虛擬機器上用戶端的音訊/視頻資料流程。</span><span class="sxs-lookup"><span data-stu-id="a8495-146">With the Microsoft Lync VDI plug-in solution, the user has to be on a Windows computer or thin client and have Microsoft's Lync VDI plugin installed to handle audio/video streams from the client on the virtual desktop.</span></span> <span data-ttu-id="a8495-147">使用者會:</span><span class="sxs-lookup"><span data-stu-id="a8495-147">A user will:</span></span>
  
1. <span data-ttu-id="a8495-148">將音訊/視頻裝置 (例如耳機或相機) 連線至本機電腦。</span><span class="sxs-lookup"><span data-stu-id="a8495-148">Connect an audio/video device (like a headset or camera) to a local computer.</span></span>
    
2. <span data-ttu-id="a8495-149">使用 Lync 2013 或商務用 Skype 2015 用戶端連線到遠端虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="a8495-149">Connect to a remote virtual desktop with a Lync 2013 or Skype for Business 2015 client.</span></span>
    
3. <span data-ttu-id="a8495-150">在虛擬機器上輸入商務用 Skype 的認證。</span><span class="sxs-lookup"><span data-stu-id="a8495-150">Enter credentials for Skype for Business on the virtual desktop.</span></span>
    
4. <span data-ttu-id="a8495-151">重新輸入使用者認證, 以與本機 Windows 電腦或瘦用戶端上的 Lync VDI 外掛程式建立連線。</span><span class="sxs-lookup"><span data-stu-id="a8495-151">Re-enter user credentials to establish a connection with the Lync VDI plug-in on the local Windows computer or thin client.</span></span>
    
<span data-ttu-id="a8495-152">建立連線之後, 使用者就已準備好撥打及接聽音訊與視頻通話。</span><span class="sxs-lookup"><span data-stu-id="a8495-152">After a connection is established, the user is ready to make and receive audio and video calls.</span></span> <span data-ttu-id="a8495-153">網路上的流量和虛擬機器上的負載都會最小化, 因為本機電腦會處理音訊/視頻處理。</span><span class="sxs-lookup"><span data-stu-id="a8495-153">Traffic on the network and the load on the virtual desktop are minimized, since the local computer handles the audio/video processing.</span></span>
  
<span data-ttu-id="a8495-154">Microsoft 的 Lync VDI 外掛程式只受特定 Windows 作業系統支援, 且只支援 Lync 2013 或商務用 Skype 2015 用戶端。</span><span class="sxs-lookup"><span data-stu-id="a8495-154">Microsoft's Lync VDI plug-in is only supported on certain Windows operating systems and only supports Lync 2013 or Skype for Business 2015 clients.</span></span> <span data-ttu-id="a8495-155">如需支援的技術與限制的詳細資料, 請參閱[支援的虛擬化技術和已知限制](vdi-environments.md#Supported_virt)。</span><span class="sxs-lookup"><span data-stu-id="a8495-155">See [Supported virtualization technologies and known limitations](vdi-environments.md#Supported_virt) for more details on supported technologies and limitations.</span></span>
  
<span data-ttu-id="a8495-156">如需詳細資訊, 請參閱下列連結:</span><span class="sxs-lookup"><span data-stu-id="a8495-156">Review the following links for more information:</span></span>
  
- [<span data-ttu-id="a8495-157">受支援的虛擬化技術與已知限制</span><span class="sxs-lookup"><span data-stu-id="a8495-157">Supported virtualization technologies and known limitations</span></span>](vdi-environments.md#Supported_virt)
    
- [<span data-ttu-id="a8495-158">Lync VDI 外掛程式先決條件</span><span class="sxs-lookup"><span data-stu-id="a8495-158">Lync VDI plug-in prerequisites</span></span>](vdi-environments.md#VDI_prereq)
    
- [<span data-ttu-id="a8495-159">使用商務用 Skype Server 部署 Lync VDI 外掛程式</span><span class="sxs-lookup"><span data-stu-id="a8495-159">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- <span data-ttu-id="a8495-160">Citrix 知識中心文章[CTX138408](https://support.citrix.com/article/CTX138408)</span><span class="sxs-lookup"><span data-stu-id="a8495-160">Citrix Knowledge Center article [CTX138408](https://support.citrix.com/article/CTX138408)</span></span>
    
<span data-ttu-id="a8495-161">您可以在[Microsoft LYNC vdi 2013 外掛程式 (32 位)](https://www.microsoft.com/en-us/download/details.aspx?id=35457)或[microsoft lync vdi 2013 外掛程式 (64 位)](https://www.microsoft.com/en-us/download/details.aspx?id=35454)中使用 microsoft VDI 外掛程式。</span><span class="sxs-lookup"><span data-stu-id="a8495-161">The Microsoft VDI plugin is available at [Microsoft Lync VDI 2013 plugin (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) or [Microsoft Lync VDI 2013 plugin (64 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35454).</span></span> <span data-ttu-id="a8495-162">商務用 Skype 2015 用戶端 (無論名稱) 都支援此外掛程式。</span><span class="sxs-lookup"><span data-stu-id="a8495-162">This plugin is supported with the Skype for Business 2015 client, despite the name.</span></span>
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a><span data-ttu-id="a8495-163">受支援的虛擬化技術與已知限制</span><span class="sxs-lookup"><span data-stu-id="a8495-163">Supported virtualization technologies and known limitations</span></span>
<span data-ttu-id="a8495-164"><a name="Supported_virt"> </a></span><span class="sxs-lookup"><span data-stu-id="a8495-164"></span></span>

<span data-ttu-id="a8495-165">Lync VDI 外掛程式可支援音訊及視頻通話 (支援的虛擬化技術)。</span><span class="sxs-lookup"><span data-stu-id="a8495-165">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="a8495-166">在遵守標準電話規章的情況下, 也包含對 E911 的支援。</span><span class="sxs-lookup"><span data-stu-id="a8495-166">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="a8495-167">下列各節說明 Lync VDI 外掛程式所支援的虛擬化技術和已知的功能限制。</span><span class="sxs-lookup"><span data-stu-id="a8495-167">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>
  
#### <a name="support-for-virtualization-technologies"></a><span data-ttu-id="a8495-168">對虛擬化技術的支援</span><span class="sxs-lookup"><span data-stu-id="a8495-168">Support for Virtualization Technologies</span></span>

<span data-ttu-id="a8495-169">Lync VDI 外掛程式支援個人虛擬桌面案例中的完整桌面遠端會話, 但在遠端桌面會話案例中則不支援。</span><span class="sxs-lookup"><span data-stu-id="a8495-169">The Lync VDI plug-in supports full desktop remote sessions in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="a8495-170">這些案例的描述如下:</span><span class="sxs-lookup"><span data-stu-id="a8495-170">These scenarios can be described as follows:</span></span>
  
- <span data-ttu-id="a8495-171">\*\*支援：個人化虛擬桌面或虛擬桌面基礎結構 (VDI)。 \*\*</span><span class="sxs-lookup"><span data-stu-id="a8495-171">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**</span></span> <span data-ttu-id="a8495-172">在這個案例中，每位使用者登入自訂的虛擬桌面，並且能儲存在所有工作階段均會顯示的桌面上的檔案。</span><span class="sxs-lookup"><span data-stu-id="a8495-172">In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="a8495-173">Microsoft 遠端桌面服務和 VMware 地平線模式是經過測試, 可搭配商務用 Skype 2015 使用的範例實現。</span><span class="sxs-lookup"><span data-stu-id="a8495-173">Microsoft Remote Desktop Services and VMware Horizon View are example implementations that have been tested for use with Skype for Business 2015.</span></span> <span data-ttu-id="a8495-174">進行驗證的其他實施包括 Citrix XenDesktop。</span><span class="sxs-lookup"><span data-stu-id="a8495-174">Other implementations undergoing validation include Citrix XenDesktop.</span></span> <span data-ttu-id="a8495-175">如需有關已由 Microsoft 測試的供應商專用 VDI 環境及用戶端硬體的相關資訊, 請參閱[Microsoft Lync 合格的基礎結構](https://go.microsoft.com/fwlink/?LinkID=313435)。</span><span class="sxs-lookup"><span data-stu-id="a8495-175">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?LinkID=313435).</span></span>
    
- <span data-ttu-id="a8495-176">\*\*不支援：遠端桌面工作階段。 \*\*</span><span class="sxs-lookup"><span data-stu-id="a8495-176">**Not supported: Remote Desktop Sessions.**</span></span> <span data-ttu-id="a8495-177">在這種情況下, 每個使用者都會登入不能自訂的一般虛擬桌面會話。</span><span class="sxs-lookup"><span data-stu-id="a8495-177">In this scenario, each user logs on to a generic virtual desktop session that can't be customized.</span></span> <span data-ttu-id="a8495-178">範例包括與 Citrix 接收器結合的 Microsoft 遠端桌面會話 (RDSH) 和 Citrix XenApp。</span><span class="sxs-lookup"><span data-stu-id="a8495-178">Examples include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>
    
<span data-ttu-id="a8495-179">Lync VDI 外掛程式不支援其他虛擬化技術 (例如應用程式虛擬化), 可讓您使用應用程式, 而不需要在本機安裝完整的應用程式。</span><span class="sxs-lookup"><span data-stu-id="a8495-179">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="a8495-180">範例實現包括 Citrix XenApp 和 Microsoft Application Virtualization (App-v)。</span><span class="sxs-lookup"><span data-stu-id="a8495-180">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="a8495-181">不支援應用程式流式處理、應用程式遠端處理及混合式虛擬化模式 (例如, 完整桌面遠端處理中的應用程式遠端處理)。</span><span class="sxs-lookup"><span data-stu-id="a8495-181">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>
  
<span data-ttu-id="a8495-182">Lync VDI 外掛程式的設計目的是使用稱為「動態虛擬通道」 (DVCs) 的平臺無關 Api。</span><span class="sxs-lookup"><span data-stu-id="a8495-182">The Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="a8495-183">針對未明確支援的案例, 請參閱來自 VDI 解決方案提供者的支援聲明。</span><span class="sxs-lookup"><span data-stu-id="a8495-183">For scenarios that are not explicitly supported, refer to support statements from the VDI solution provider.</span></span>
  
#### <a name="lync-vdi-plug-in-prerequisites"></a><span data-ttu-id="a8495-184">Lync VDI 外掛程式先決條件</span><span class="sxs-lookup"><span data-stu-id="a8495-184">Lync VDI plug-in prerequisites</span></span>
<span data-ttu-id="a8495-185"><a name="VDI_prereq"> </a></span><span class="sxs-lookup"><span data-stu-id="a8495-185"></span></span>

<span data-ttu-id="a8495-186">在 VDI 環境中, 虛擬機器與使用者的本機電腦必須符合本節中所述的需求。</span><span class="sxs-lookup"><span data-stu-id="a8495-186">In a VDI environment, the virtual machines and the user's local computer must meet the requirements outlined in this section.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="a8495-187">您的虛擬化解決方案提供者可以提供如何安裝及部署其環境的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a8495-187">Your virtualization solution provider can supply details about how to install and deploy their environment.</span></span> <span data-ttu-id="a8495-188">如需有關根據 Hyper-v 和遠端桌面服務部署虛擬化環境的一般資訊, 請參閱 Microsoft 文件庫中的下列文章: [hyper-v](https://go.microsoft.com/fwlink/p/?linkid=247514)、 [Windows Server 2008 R2 中的遠端桌面服務](https://go.microsoft.com/fwlink/p/?linkid=247513)</span><span class="sxs-lookup"><span data-stu-id="a8495-188">For general information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft Library: [Hyper-V](https://go.microsoft.com/fwlink/p/?linkid=247514), [Remote Desktop Services in Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513)</span></span> 
  
<span data-ttu-id="a8495-189">虛擬機器必須使用 Windows 8、Windows 7 或 Windows Server 2008 R2 (含最新的 service pack) 進行設定。</span><span class="sxs-lookup"><span data-stu-id="a8495-189">Virtual machines must be configured with Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>
  
<span data-ttu-id="a8495-190">使用者的本機電腦必須符合下列需求:</span><span class="sxs-lookup"><span data-stu-id="a8495-190">The user's local computer must meet the following requirements:</span></span>
  
- <span data-ttu-id="a8495-191">使用者必須駐留在商務用 Skype Server 或 Lync Server 2013 上。</span><span class="sxs-lookup"><span data-stu-id="a8495-191">The user must be homed on Skype for Business Server or Lync Server 2013.</span></span>
    
- <span data-ttu-id="a8495-192">本機電腦必須執行 Windows Embedded Standard 7 (含 SP1)、Windows 7 (含 SP1) 或 Windows 8。</span><span class="sxs-lookup"><span data-stu-id="a8495-192">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, or Windows 8.</span></span>
    
- <span data-ttu-id="a8495-193">如果您使用的是遠端桌面服務, 請選擇32位或64位的 Lync VDI 外掛程式, 以符合本機電腦的作業系統。</span><span class="sxs-lookup"><span data-stu-id="a8495-193">If you're using Remote Desktop Services, choose the 32-bit or 64-bit Lync VDI plug-in to match the local computer's operating system.</span></span> <span data-ttu-id="a8495-194">本機電腦和虛擬電腦不需要有32位或64位的作業系統。</span><span class="sxs-lookup"><span data-stu-id="a8495-194">It's not required for both the local computer and the virtual machine to have 32-bit or 64-bit operating systems.</span></span> <span data-ttu-id="a8495-195">如果您使用的是其他虛擬化解決方案或平臺, 請參閱提供者的需求。</span><span class="sxs-lookup"><span data-stu-id="a8495-195">If you're using another virtualization solution or platform, refer to your provider's requirements.</span></span>
    
- <span data-ttu-id="a8495-196">本機電腦必須執行[最新版本的遠端桌面用戶端](https://go.microsoft.com/fwlink/p/?LinkId=268032)。</span><span class="sxs-lookup"><span data-stu-id="a8495-196">The local computer must be running the [latest version of the remote desktop client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span> <span data-ttu-id="a8495-197">從您的虛擬化方案提供者, 從 Microsoft 或最新的遠端桌面用戶端軟體, 安裝遠端桌面服務用戶端的最新更新。</span><span class="sxs-lookup"><span data-stu-id="a8495-197">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> 
    
- <span data-ttu-id="a8495-198">在本機電腦上, 必須設定遠端桌面用戶端設定, 以便在本機電腦上播放音訊, 並停用遠端錄製。</span><span class="sxs-lookup"><span data-stu-id="a8495-198">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="a8495-199">若要在 Windows 中設定遠端桌面連線的這些設定, 請參閱下一節「設定遠端桌面連線設定」。</span><span class="sxs-lookup"><span data-stu-id="a8495-199">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span> 
    
<span data-ttu-id="a8495-200">您可以在[Microsoft LYNC vdi 2013 外掛程式 (32 位)](https://www.microsoft.com/en-us/download/details.aspx?id=35457)或[microsoft lync vdi 2013 外掛程式 (64 位)](https://www.microsoft.com/en-us/download/details.aspx?id=35454)中使用 microsoft VDI 外掛程式。</span><span class="sxs-lookup"><span data-stu-id="a8495-200">The Microsoft VDI plugin is available at [Microsoft Lync VDI 2013 plugin (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) or [Microsoft Lync VDI 2013 plugin (64 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35454).</span></span>
  
#### <a name="known-feature-limitations"></a><span data-ttu-id="a8495-201">已知的功能限制</span><span class="sxs-lookup"><span data-stu-id="a8495-201">Known Feature Limitations</span></span>
<span data-ttu-id="a8495-202"><a name="VDI_prereq"> </a></span><span class="sxs-lookup"><span data-stu-id="a8495-202"></span></span>

<span data-ttu-id="a8495-203">當您在 VDI 環境中使用商務用 Skype 2015 用戶端時, 以下是已知的限制:</span><span class="sxs-lookup"><span data-stu-id="a8495-203">The following are known limitations when you use the Skype for Business 2015 client in a VDI environment:</span></span>
  
<span data-ttu-id="a8495-204">通話委派與回應群組代理匿名功能的支援有限。</span><span class="sxs-lookup"><span data-stu-id="a8495-204">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>
  
<span data-ttu-id="a8495-205">不支援以下功能：</span><span class="sxs-lookup"><span data-stu-id="a8495-205">There is no support for the following features:</span></span>
  
- <span data-ttu-id="a8495-206">整合式音訊裝置及視訊裝置調整頁面。</span><span class="sxs-lookup"><span data-stu-id="a8495-206">Integrated Audio Device and Video Device tuning pages.</span></span>
    
- <span data-ttu-id="a8495-207">多重檢視視訊。</span><span class="sxs-lookup"><span data-stu-id="a8495-207">Multiple-view video.</span></span>
    
- <span data-ttu-id="a8495-208">錄製交談。</span><span class="sxs-lookup"><span data-stu-id="a8495-208">Recording of conversations.</span></span>
    
- <span data-ttu-id="a8495-209">匿名加入會議 (也就是加入不與貴組織聯盟之組織託管的商務用 Skype 會議)。</span><span class="sxs-lookup"><span data-stu-id="a8495-209">Joining meetings anonymously (that is, joining Skype for Business meetings hosted by an organization that does not federate with your organization).</span></span>
    
- <span data-ttu-id="a8495-210">將 Lync VDI 外掛程式與 Lync Phone Edition 裝置搭配使用。</span><span class="sxs-lookup"><span data-stu-id="a8495-210">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
- <span data-ttu-id="a8495-211">在網路中斷連線的情況下延續通話。</span><span class="sxs-lookup"><span data-stu-id="a8495-211">Call continuity in case of a network outage.</span></span>
    
- <span data-ttu-id="a8495-212">自訂鈴聲及通話保留音樂功能。</span><span class="sxs-lookup"><span data-stu-id="a8495-212">Customized ringtones and music-on-hold features.</span></span>
    
<span data-ttu-id="a8495-213">在 Office 365 環境中不支援 Lync VDI 外掛程式。</span><span class="sxs-lookup"><span data-stu-id="a8495-213">The Lync VDI plug-in is not supported in an Office 365 environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a8495-214">Citrix 即時優化套件支援 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a8495-214">The Citrix RealTime Optimization Pack does support Office 365.</span></span> <span data-ttu-id="a8495-215">針對基於 Citrix 的虛擬環境, 請參閱 Citrix 的[技術綜述](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl)檔, 瞭解支援的功能和版本清單。</span><span class="sxs-lookup"><span data-stu-id="a8495-215">For Citrix-based virtual environments, review Citrix's [Technical Overview](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) documentation for the list of supported features and versions.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a8495-216">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a8495-216">See also</span></span>
<span data-ttu-id="a8495-217"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="a8495-217"></span></span>

[<span data-ttu-id="a8495-218">使用商務用 Skype Server 部署 Lync VDI 外掛程式</span><span class="sxs-lookup"><span data-stu-id="a8495-218">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

