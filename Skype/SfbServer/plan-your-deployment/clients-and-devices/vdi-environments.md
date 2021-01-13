---
title: 規劃 VDI 環境中的商務用 Skype
author: cichur
ms.author: v-cichur
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: 本主題討論連接至遠端虛擬桌面時使用商務用 Skype 的規劃考慮。
ms.openlocfilehash: 66fe9dd0be2dd079597837b8d25c29b3f047b0c6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816103"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a><span data-ttu-id="645f9-103">規劃 VDI 環境中的商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="645f9-103">Plan for Skype for Business in VDI environments</span></span>
 
<span data-ttu-id="645f9-104">本主題討論連接至遠端虛擬桌面時使用商務用 Skype 的規劃考慮。</span><span class="sxs-lookup"><span data-stu-id="645f9-104">This topic discusses planning considerations for using Skype for Business while connecting to a remote virtual desktop.</span></span> 
  
<span data-ttu-id="645f9-105">在安全性與合規性問題尤其敏感的某些組織中，會使用 (VDI) 環境的虛擬桌面基礎結構。</span><span class="sxs-lookup"><span data-stu-id="645f9-105">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="645f9-106">他們的使用者可以使用遠端桌面服務或類似的遠端連線，在虛擬桌面執行其所有的桌面應用程式和檔案。</span><span class="sxs-lookup"><span data-stu-id="645f9-106">Their users do their work on a virtual desktop with all their desktop applications and files using Remote Desktop Services or a similar remote connection.</span></span> <span data-ttu-id="645f9-107">在連接上使用商務用 Skype （如這類連線）需要大量載入在虛擬機器上之用戶端的音訊和視頻處理。</span><span class="sxs-lookup"><span data-stu-id="645f9-107">Using Skype for Business with full audio and video on a connection like that requires heavy loads of audio and video processing on the client homed on a virtual desktop.</span></span> <span data-ttu-id="645f9-108">其他的 VDI 外掛程式軟體可讓您將處理常式降至使用者的本機電腦，並減少虛擬機器的負載。</span><span class="sxs-lookup"><span data-stu-id="645f9-108">Additional VDI plug-in software is available that offloads that processing to the end user's local machine, and reduces the load on the virtual desktop.</span></span>
  
<span data-ttu-id="645f9-109">有三個可用於 VDI 外掛程式元件的解決方案，由 Microsoft、Citrix 或 VMWare 提供。</span><span class="sxs-lookup"><span data-stu-id="645f9-109">There are three solutions available for the VDI plug-in component, offered by Microsoft, Citrix, or VMWare.</span></span> <span data-ttu-id="645f9-110">針對新的部署，Microsoft 建議使用 Citrix HDX 即時優化套件解決方案或 VMWare 地平線虛擬化套件。</span><span class="sxs-lookup"><span data-stu-id="645f9-110">For new deployments, Microsoft recommends using either the Citrix HDX RealTime Optimization Pack solution or the VMWare Horizon Virtualization Pack.</span></span> <span data-ttu-id="645f9-111">原始的 Lync VDI 外掛程式仍可支援其生命週期的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="645f9-111">The original Lync VDI Plug-in is still supported for the remainder of its lifecycle.</span></span>
  
- <span data-ttu-id="645f9-112">**Lync 的 VDI 外掛程式** 是針對 lync 2013 開發的，且與 lync 2013 或商務用 Skype 2015 用戶端在虛擬機器上的相容性。</span><span class="sxs-lookup"><span data-stu-id="645f9-112">The **Lync VDI plug-in** was developed for Lync 2013 and is compatible with either the Lync 2013 or Skype for Business 2015 client running on a virtual desktop.</span></span> <span data-ttu-id="645f9-113">它是安裝在本機電腦上的獨立應用程式，可讓本機音訊和影片裝置使用於虛擬機器上的用戶端。</span><span class="sxs-lookup"><span data-stu-id="645f9-113">It's a stand-alone application that installs on the local computer and allows the use of local audio and video devices with a client on a virtual desktop.</span></span> <span data-ttu-id="645f9-114">外掛程式不需要在本機電腦或瘦用戶端上安裝商務用 Skype 用戶端，必須執行 Windows 7、Windows 8 或 Windows Server 2008 作業系統。</span><span class="sxs-lookup"><span data-stu-id="645f9-114">The plug-in does not require a Skype for Business client to be installed on the local computer or thin client, which must run Windows 7, Windows 8, or Windows Server 2008 operating systems.</span></span> <span data-ttu-id="645f9-115">使用這些作業系統及 Microsoft 支援的瘦用戶端裝置 (包括： Dell Wyse Z90D7、Dell Wyse R90L7、Dell Wyse X90m7、HP t610 和 HP t5740e。 ) 仍支援此外掛程式，但不會規劃未來的更新。</span><span class="sxs-lookup"><span data-stu-id="645f9-115">(Thin client devices using these operating systems and supported by Microsoft include: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 and HP t5740e.) This plug-in is still supported, but no future updates are planned.</span></span> <span data-ttu-id="645f9-116">針對 Citrix 型虛擬環境，建議使用 Citrix 即時優化套件。</span><span class="sxs-lookup"><span data-stu-id="645f9-116">For Citrix-based virtual environments, the Citrix RealTime Optimization Pack is recommended.</span></span>
    
- <span data-ttu-id="645f9-117">在 Lync VDI 外掛程式上建立 **Citrix 即時優化套件** ，並在虛擬機器上與 lync 2013 或商務用 Skype 2016 用戶端搭配使用。</span><span class="sxs-lookup"><span data-stu-id="645f9-117">The **Citrix RealTime Optimization Pack** builds on the Lync VDI plug-in and works with Lync 2013 or Skype for Business 2016 clients on a virtual desktop.</span></span> <span data-ttu-id="645f9-118">它是由 Citrix 和 Microsoft 共同開發，可在原始的 VDI 外掛程式進行改進。</span><span class="sxs-lookup"><span data-stu-id="645f9-118">It was co-developed by Citrix and Microsoft to improve upon the original VDI Plug-in.</span></span> <span data-ttu-id="645f9-119">它可以安裝在具有 Windows 和非 Windows 作業系統的用戶端， (包括 Windows 10、Mac 和 Linux) 。</span><span class="sxs-lookup"><span data-stu-id="645f9-119">It can be installed on clients with Windows and non-Windows operating systems (including Windows 10, Mac and Linux).</span></span> <span data-ttu-id="645f9-120">它包含兩個元件：在虛擬機器上安裝的即時連接器 (，也就是安裝在使用者本機電腦) 上的即時媒體引擎) 和即時媒體引擎 (。</span><span class="sxs-lookup"><span data-stu-id="645f9-120">It consists of two components: the RealTime Connector (which is installed on the virtual desktop) and the RealTime Media Engine (which is installed on the end user's local machine).</span></span> <span data-ttu-id="645f9-121">這兩個元件可讓使用者的本機電腦使用在虛擬機器上執行的商務用 Skype 用戶端，將 A/V 處理移至本機電腦。</span><span class="sxs-lookup"><span data-stu-id="645f9-121">These two components allow the user's local computer to use the Skype for Business client running on the virtual desktop with the A/V processing moved to the local computer.</span></span> <span data-ttu-id="645f9-122">針對 Citrix 型虛擬桌面環境，建議使用 Citrix 即時優化套件，並規劃進一步的支援。</span><span class="sxs-lookup"><span data-stu-id="645f9-122">For Citrix-based virtual desktop environments, the Citrix RealTime Optimization Pack is recommended, and further support is planned.</span></span>
    
- <span data-ttu-id="645f9-123">適用于商務用 Skype 的 **VMWare 地平線虛擬化套件** （與 VMWare 共同開發）可讓您在虛擬桌面中傳遞商務用 skype，同時提供極佳的使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="645f9-123">The **VMWare Horizon Virtualization Pack** for Skype for Business, developed in collaboration with VMWare, allows you to deliver Skype for Business in a virtual desktop while delivering a great user experience.</span></span> <span data-ttu-id="645f9-124">此解決方案的運作方式是利用用戶端的媒體引擎建立優化的解決方案，用戶端端點提供媒體卸載功能以進行音訊和視頻通話。</span><span class="sxs-lookup"><span data-stu-id="645f9-124">The solution works by leveraging a media engine at the client to create an optimized solution, with the client endpoint providing media offload capabilities for audio and video calls.</span></span> <span data-ttu-id="645f9-125">這種解決方案可以直接在端點之間傳送一個單一的共同作業，或將其卸載至中央 Multipoint Control Unit (MCU) ，以供多方會議通話或會議使用。</span><span class="sxs-lookup"><span data-stu-id="645f9-125">This solution that can deliver audio and video either directly between endpoints for one-on-one collaboration, or offload it to a central Multipoint Control Unit (MCU) for multiparty conference calls or meetings.</span></span>
    
> [!NOTE]
> <span data-ttu-id="645f9-126">在 Citrix HDX 即時優化套件或 VMWare 地平線虛擬化套件中，不支援商務用 Skype Basic 用戶端。</span><span class="sxs-lookup"><span data-stu-id="645f9-126">The Skype for Business Basic clients are not supported with the Citrix HDX RealTime Optimization Pack or the VMWare Horizon Virtualization Pack.</span></span> 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a><span data-ttu-id="645f9-127">Citrix HDX 即時優化套件</span><span class="sxs-lookup"><span data-stu-id="645f9-127">Citrix HDX RealTime Optimization Pack</span></span>
<span data-ttu-id="645f9-128"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="645f9-128"><a name="Citrix_RT"> </a></span></span>

<span data-ttu-id="645f9-129">Citrix 的 VDI 環境外掛程式 (XenApp 和 XenDesktop) 的功能可與 Lync 2013 和商務用 Skype 2015 及 2016 (完全用戶端使用任何按一下以執行安裝程式，或在已安裝于虛擬機器上的用戶端年 1 2017 月的版本中所發行的 MSI 安裝程式相容。</span><span class="sxs-lookup"><span data-stu-id="645f9-129">Citrix's VDI environment plugin (a feature of XenApp and XenDesktop) is compatible with Lync 2013 and Skype for Business 2015 and 2016 (Full clients using any click to run installer, or MSI installers released after January 2017 PU) clients installed on a virtual desktop.</span></span> <span data-ttu-id="645f9-130">其整體運作是以 Microsoft Lync VDI 外掛程式為基礎，但可在更廣泛的用戶端作業系統上運作，包括 Windows 10、Macintosh 及 Linux。</span><span class="sxs-lookup"><span data-stu-id="645f9-130">Its overall functioning is based on the Microsoft Lync VDI plug-in, but works on a wider variety of client operating systems, including Windows 10, Macintosh, and Linux.</span></span>
  
<span data-ttu-id="645f9-131">在將 [Microsoft 商務用 Skype 傳送至 XenApp 和 XenDesktop 使用者](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)的 Citrix 網站上，可以找到完整的功能和支援的技術清單。</span><span class="sxs-lookup"><span data-stu-id="645f9-131">A full list of features and supported technologies can be found on the Citrix website at [Delivering Microsoft Skype for Business to XenApp and XenDesktop Users](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).</span></span>
  
<span data-ttu-id="645f9-132">如需詳細資訊，請參閱下列連結：</span><span class="sxs-lookup"><span data-stu-id="645f9-132">Review the following links for more information:</span></span>
  
- <span data-ttu-id="645f9-133">Citrix [HDX 即時優化套件 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)</span><span class="sxs-lookup"><span data-stu-id="645f9-133">Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)</span></span>
    
- [<span data-ttu-id="645f9-134">技術概述</span><span class="sxs-lookup"><span data-stu-id="645f9-134">Technical Overview</span></span>](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [<span data-ttu-id="645f9-135">CTX200279 商務用 Skype 功能支援</span><span class="sxs-lookup"><span data-stu-id="645f9-135">CTX200279 Skype for Business Feature Support</span></span>](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a><span data-ttu-id="645f9-136">VMWare 地平線虛擬化套件</span><span class="sxs-lookup"><span data-stu-id="645f9-136">VMWare Horizon Virtualization Pack</span></span>
<span data-ttu-id="645f9-137"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="645f9-137"><a name="Citrix_RT"> </a></span></span>

<span data-ttu-id="645f9-138">VMWare 的 VDI 環境解決方案與在虛擬機器上安裝的商務用 Skype 2015 和2016完整用戶端相容。</span><span class="sxs-lookup"><span data-stu-id="645f9-138">VMWare's VDI environment solution is compatible with Skype for Business 2015 and 2016 Full clients installed on a virtual desktop.</span></span> <span data-ttu-id="645f9-139">其整體運作是以 Microsoft Lync VDI 外掛程式為基礎，但可在更廣泛的用戶端作業系統上運作，包括 Windows 10、Macintosh 及 Linux。</span><span class="sxs-lookup"><span data-stu-id="645f9-139">Its overall functioning is based on the Microsoft Lync VDI plug-in, but works on a wider variety of client operating systems, including Windows 10, Macintosh, and Linux.</span></span> 
  
<span data-ttu-id="645f9-140">您可以在 VMWare 網站上透過下列連結找到功能及支援技術的完整討論：</span><span class="sxs-lookup"><span data-stu-id="645f9-140">A full discussion of features and supported technologies can be found on the VMWare website at the following links:</span></span>
  
- [<span data-ttu-id="645f9-141">VMware 地平線 7.4 &amp; 水準用戶端4.7 的新功能</span><span class="sxs-lookup"><span data-stu-id="645f9-141">What's New in VMware Horizon 7.4 &amp; Horizon Client 4.7</span></span>](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [<span data-ttu-id="645f9-142">商務用 Skype 的地平線虛擬化套件</span><span class="sxs-lookup"><span data-stu-id="645f9-142">Horizon Virtualization Pack for Skype for Business</span></span>](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [<span data-ttu-id="645f9-143">使用 VMWare 範圍的 Microsoft 商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="645f9-143">Microsoft Skype for Business With VMWare Horizon</span></span>](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a><span data-ttu-id="645f9-144">Microsoft 的 Lync VDI 外掛程式</span><span class="sxs-lookup"><span data-stu-id="645f9-144">Microsoft's Lync VDI plug-in</span></span>
<span data-ttu-id="645f9-145"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="645f9-145"><a name="Citrix_RT"> </a></span></span>

<span data-ttu-id="645f9-146">透過 Microsoft Lync VDI 外掛程式解決方案，使用者必須在 Windows 電腦或瘦用戶端上，並已安裝 Microsoft 的 Lync VDI 外掛程式，以處理來自虛擬機器上之用戶端的音訊/視頻資料流程。</span><span class="sxs-lookup"><span data-stu-id="645f9-146">With the Microsoft Lync VDI plug-in solution, the user has to be on a Windows computer or thin client and have Microsoft's Lync VDI plugin installed to handle audio/video streams from the client on the virtual desktop.</span></span> <span data-ttu-id="645f9-147">使用者將會：</span><span class="sxs-lookup"><span data-stu-id="645f9-147">A user will:</span></span>
  
1. <span data-ttu-id="645f9-148">將音訊/影片裝置 (像耳機或相機) 連接至本機電腦。</span><span class="sxs-lookup"><span data-stu-id="645f9-148">Connect an audio/video device (like a headset or camera) to a local computer.</span></span>
    
2. <span data-ttu-id="645f9-149">使用 Lync 2013 或商務用 Skype 2015 用戶端連接至遠端虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="645f9-149">Connect to a remote virtual desktop with a Lync 2013 or Skype for Business 2015 client.</span></span>
    
3. <span data-ttu-id="645f9-150">輸入虛擬機器上商務用 Skype 的認證。</span><span class="sxs-lookup"><span data-stu-id="645f9-150">Enter credentials for Skype for Business on the virtual desktop.</span></span>
    
4. <span data-ttu-id="645f9-151">重新輸入使用者認證，以與本機 Windows 電腦或瘦用戶端上的 Lync VDI 外掛程式建立連線。</span><span class="sxs-lookup"><span data-stu-id="645f9-151">Re-enter user credentials to establish a connection with the Lync VDI plug-in on the local Windows computer or thin client.</span></span>
    
<span data-ttu-id="645f9-152">建立連線之後，使用者就可以開始和接收音訊和影片通話。</span><span class="sxs-lookup"><span data-stu-id="645f9-152">After a connection is established, the user is ready to make and receive audio and video calls.</span></span> <span data-ttu-id="645f9-153">網路上的流量和虛擬機器上的負載會最小化，因為本機電腦會處理音訊/視頻處理。</span><span class="sxs-lookup"><span data-stu-id="645f9-153">Traffic on the network and the load on the virtual desktop are minimized, since the local computer handles the audio/video processing.</span></span>
  
<span data-ttu-id="645f9-154">Microsoft 的 Lync VDI 外掛程式只有在某些 Windows 作業系統上受到支援，且只支援 Lync 2013 或商務用 Skype 2015 用戶端。</span><span class="sxs-lookup"><span data-stu-id="645f9-154">Microsoft's Lync VDI plug-in is only supported on certain Windows operating systems and only supports Lync 2013 or Skype for Business 2015 clients.</span></span> <span data-ttu-id="645f9-155">如需支援的技術和限制，請參閱 [支援的虛擬化技術與已知限制](vdi-environments.md#Supported_virt) 。</span><span class="sxs-lookup"><span data-stu-id="645f9-155">See [Supported virtualization technologies and known limitations](vdi-environments.md#Supported_virt) for more details on supported technologies and limitations.</span></span>
  
<span data-ttu-id="645f9-156">如需詳細資訊，請參閱下列連結：</span><span class="sxs-lookup"><span data-stu-id="645f9-156">Review the following links for more information:</span></span>
  
- [<span data-ttu-id="645f9-157">支援的虛擬化技術與已知限制</span><span class="sxs-lookup"><span data-stu-id="645f9-157">Supported virtualization technologies and known limitations</span></span>](vdi-environments.md#Supported_virt)
    
- [<span data-ttu-id="645f9-158">Lync VDI 外掛程式必要條件</span><span class="sxs-lookup"><span data-stu-id="645f9-158">Lync VDI plug-in prerequisites</span></span>](vdi-environments.md#VDI_prereq)
    
- [<span data-ttu-id="645f9-159">使用商務用 Skype Server 部署 Lync VDI 外掛程式</span><span class="sxs-lookup"><span data-stu-id="645f9-159">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- <span data-ttu-id="645f9-160">Citrix 知識中心文章 [CTX138408](https://support.citrix.com/article/CTX138408)</span><span class="sxs-lookup"><span data-stu-id="645f9-160">Citrix Knowledge Center article [CTX138408](https://support.citrix.com/article/CTX138408)</span></span>
    
<span data-ttu-id="645f9-161">Microsoft VDI 外掛程式可從 [Microsoft LYNC vdi 2013 外掛程式 (32 位) ](https://www.microsoft.com/download/details.aspx?id=35457) 或 [microsoft Lync vdi 2013 外掛程式 (64 bit) ](https://www.microsoft.com/download/details.aspx?id=35454)。</span><span class="sxs-lookup"><span data-stu-id="645f9-161">The Microsoft VDI plugin is available at [Microsoft Lync VDI 2013 plugin (32 bit)](https://www.microsoft.com/download/details.aspx?id=35457) or [Microsoft Lync VDI 2013 plugin (64 bit)](https://www.microsoft.com/download/details.aspx?id=35454).</span></span> <span data-ttu-id="645f9-162">雖然商務用 Skype 2015 用戶端也支援此外掛程式，但名稱卻是。</span><span class="sxs-lookup"><span data-stu-id="645f9-162">This plugin is supported with the Skype for Business 2015 client, despite the name.</span></span>
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a><span data-ttu-id="645f9-163">支援的虛擬化技術與已知限制</span><span class="sxs-lookup"><span data-stu-id="645f9-163">Supported virtualization technologies and known limitations</span></span>
<span data-ttu-id="645f9-164"><a name="Supported_virt"> </a></span><span class="sxs-lookup"><span data-stu-id="645f9-164"><a name="Supported_virt"> </a></span></span>

<span data-ttu-id="645f9-165">Lync VDI 外掛程式允許音訊和視頻通話支援的虛擬化技術。</span><span class="sxs-lookup"><span data-stu-id="645f9-165">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="645f9-166">在遵守標準電話規定時，也會包含對 E911 的支援。</span><span class="sxs-lookup"><span data-stu-id="645f9-166">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="645f9-167">下列各節說明 Lync VDI 外掛程式支援的虛擬化技術與已知的功能限制。</span><span class="sxs-lookup"><span data-stu-id="645f9-167">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>
  
#### <a name="support-for-virtualization-technologies"></a><span data-ttu-id="645f9-168">虛擬化技術的支援</span><span class="sxs-lookup"><span data-stu-id="645f9-168">Support for Virtualization Technologies</span></span>

<span data-ttu-id="645f9-169">Lync VDI 外掛程式支援個人虛擬桌面案例中的完整桌面遠端會話，但不支援在遠端桌面會話案例中。</span><span class="sxs-lookup"><span data-stu-id="645f9-169">The Lync VDI plug-in supports full desktop remote sessions in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="645f9-170">您可以將這些案例描述如下：</span><span class="sxs-lookup"><span data-stu-id="645f9-170">These scenarios can be described as follows:</span></span>
  
- <span data-ttu-id="645f9-171">**支援：個人化虛擬桌面或虛擬桌面基礎結構 (VDI) 。**</span><span class="sxs-lookup"><span data-stu-id="645f9-171">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**</span></span> <span data-ttu-id="645f9-172">在此案例中，每一位使用者都登入至可自訂的虛擬桌面機，而且能夠將保留在會話中的檔案儲存在桌面機上。</span><span class="sxs-lookup"><span data-stu-id="645f9-172">In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="645f9-173">Microsoft 遠端桌面服務和 VMware 地平線模式是已測試為搭配商務用 Skype 2015 使用的範例實施方案。</span><span class="sxs-lookup"><span data-stu-id="645f9-173">Microsoft Remote Desktop Services and VMware Horizon View are example implementations that have been tested for use with Skype for Business 2015.</span></span> <span data-ttu-id="645f9-174">其他進行驗證的實施包括 Citrix XenDesktop。</span><span class="sxs-lookup"><span data-stu-id="645f9-174">Other implementations undergoing validation include Citrix XenDesktop.</span></span> <span data-ttu-id="645f9-175">如需廠商特有的 VDI 環境及已由 Microsoft 測試的用戶端硬體資訊，請參閱 [Microsoft Lync 的基礎結構限定](https://go.microsoft.com/fwlink/?LinkID=313435)。</span><span class="sxs-lookup"><span data-stu-id="645f9-175">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?LinkID=313435).</span></span>
    
- <span data-ttu-id="645f9-176">**不支援：遠端桌面會話。**</span><span class="sxs-lookup"><span data-stu-id="645f9-176">**Not supported: Remote Desktop Sessions.**</span></span> <span data-ttu-id="645f9-177">在此案例中，每一位使用者都登入無法自訂的一般虛擬桌面會話。</span><span class="sxs-lookup"><span data-stu-id="645f9-177">In this scenario, each user logs on to a generic virtual desktop session that can't be customized.</span></span> <span data-ttu-id="645f9-178">範例包括 (RDSH) 和 Citrix XenApp 結合 Citrix 接收器的 Microsoft 遠端桌面會話。</span><span class="sxs-lookup"><span data-stu-id="645f9-178">Examples include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>
    
<span data-ttu-id="645f9-179">Lync VDI 外掛程式不支援其他虛擬化技術（例如 application virtualization），允許使用應用程式，而不需要在本機安裝完整的應用程式。</span><span class="sxs-lookup"><span data-stu-id="645f9-179">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="645f9-180">範例實現包括 Citrix XenApp 和 Microsoft Application Virtualization (App-V) 。</span><span class="sxs-lookup"><span data-stu-id="645f9-180">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="645f9-181">應用程式流式處理、應用程式遠端處理和混合虛擬化模式 (例如，不支援完整桌面遠端) 中的應用程式遠端處理。</span><span class="sxs-lookup"><span data-stu-id="645f9-181">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>
  
<span data-ttu-id="645f9-182">Lync VDI 外掛程式的設計目的是使用獨立于平臺的 APIs，稱為動態虛擬通道 (Dvc) 。</span><span class="sxs-lookup"><span data-stu-id="645f9-182">The Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="645f9-183">針對未明確支援的案例，請參閱 VDI 解決方案提供者的支援聲明。</span><span class="sxs-lookup"><span data-stu-id="645f9-183">For scenarios that are not explicitly supported, refer to support statements from the VDI solution provider.</span></span>
  
#### <a name="lync-vdi-plug-in-prerequisites"></a><span data-ttu-id="645f9-184">Lync VDI 外掛程式必要條件</span><span class="sxs-lookup"><span data-stu-id="645f9-184">Lync VDI plug-in prerequisites</span></span>
<span data-ttu-id="645f9-185"><a name="VDI_prereq"> </a></span><span class="sxs-lookup"><span data-stu-id="645f9-185"><a name="VDI_prereq"> </a></span></span>

<span data-ttu-id="645f9-186">在 VDI 環境中，虛擬機器和使用者的本機電腦必須符合本節所述的需求。</span><span class="sxs-lookup"><span data-stu-id="645f9-186">In a VDI environment, the virtual machines and the user's local computer must meet the requirements outlined in this section.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="645f9-187">您的虛擬化解決方案供應商可以提供如何安裝及部署其環境的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="645f9-187">Your virtualization solution provider can supply details about how to install and deploy their environment.</span></span> <span data-ttu-id="645f9-188">如需根據 Hyper-V 和遠端桌面服務部署虛擬化環境的一般資訊，請參閱 Microsoft Library 中的下列文章： [Hyper-V](https://go.microsoft.com/fwlink/p/?linkid=247514)， [遠端桌面服務，在 Windows Server 2008 R2 中](https://go.microsoft.com/fwlink/p/?linkid=247513)</span><span class="sxs-lookup"><span data-stu-id="645f9-188">For general information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft Library: [Hyper-V](https://go.microsoft.com/fwlink/p/?linkid=247514), [Remote Desktop Services in Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513)</span></span> 
  
<span data-ttu-id="645f9-189">虛擬機器必須設定 Windows 8、Windows 7 或 Windows Server 2008 R2 搭配最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="645f9-189">Virtual machines must be configured with Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>
  
<span data-ttu-id="645f9-190">使用者的本機電腦必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="645f9-190">The user's local computer must meet the following requirements:</span></span>
  
- <span data-ttu-id="645f9-191">使用者必須位於商務用 Skype Server 或 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="645f9-191">The user must be homed on Skype for Business Server or Lync Server 2013.</span></span>
    
- <span data-ttu-id="645f9-192">本機電腦必須執行 Windows Embedded Standard 7 搭配 SP1、Windows 7 搭配 SP1 或 Windows 8。</span><span class="sxs-lookup"><span data-stu-id="645f9-192">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, or Windows 8.</span></span>
    
- <span data-ttu-id="645f9-193">如果您使用的是遠端桌面服務，請選擇32位或64位的 Lync VDI 外掛程式，以符合本機電腦的作業系統。</span><span class="sxs-lookup"><span data-stu-id="645f9-193">If you're using Remote Desktop Services, choose the 32-bit or 64-bit Lync VDI plug-in to match the local computer's operating system.</span></span> <span data-ttu-id="645f9-194">本機電腦和虛擬機器都不需要有32位或64位作業系統。</span><span class="sxs-lookup"><span data-stu-id="645f9-194">It's not required for both the local computer and the virtual machine to have 32-bit or 64-bit operating systems.</span></span> <span data-ttu-id="645f9-195">如果您使用的是其他虛擬化解決方案或平臺，請參閱提供者的需求。</span><span class="sxs-lookup"><span data-stu-id="645f9-195">If you're using another virtualization solution or platform, refer to your provider's requirements.</span></span>
    
- <span data-ttu-id="645f9-196">本機電腦必須執行 [最新版本的遠端桌面用戶端](https://go.microsoft.com/fwlink/p/?LinkId=268032)。</span><span class="sxs-lookup"><span data-stu-id="645f9-196">The local computer must be running the [latest version of the remote desktop client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span> <span data-ttu-id="645f9-197">從 Microsoft 或您的虛擬化解決方案供應商，安裝遠端桌面服務用戶端的最新更新（或最新的遠端桌面用戶端軟體）。</span><span class="sxs-lookup"><span data-stu-id="645f9-197">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> 
    
- <span data-ttu-id="645f9-198">在本機電腦上，必須設定遠端桌面用戶端設定，以便在本機電腦上播放音訊，並停用遠端錄製。</span><span class="sxs-lookup"><span data-stu-id="645f9-198">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="645f9-199">若要在 Windows 中為遠端桌面連線設定這些設定，請參閱下一節「設定遠端桌面連線設定」。</span><span class="sxs-lookup"><span data-stu-id="645f9-199">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span> 
    
<span data-ttu-id="645f9-200">Microsoft VDI 外掛程式可從 [Microsoft LYNC vdi 2013 外掛程式 (32 位) ](https://www.microsoft.com/download/details.aspx?id=35457) 或 [microsoft Lync vdi 2013 外掛程式 (64 bit) ](https://www.microsoft.com/download/details.aspx?id=35454)。</span><span class="sxs-lookup"><span data-stu-id="645f9-200">The Microsoft VDI plugin is available at [Microsoft Lync VDI 2013 plugin (32 bit)](https://www.microsoft.com/download/details.aspx?id=35457) or [Microsoft Lync VDI 2013 plugin (64 bit)](https://www.microsoft.com/download/details.aspx?id=35454).</span></span>
  
#### <a name="known-feature-limitations"></a><span data-ttu-id="645f9-201">已知的功能限制</span><span class="sxs-lookup"><span data-stu-id="645f9-201">Known Feature Limitations</span></span>
<span data-ttu-id="645f9-202"><a name="VDI_prereq"> </a></span><span class="sxs-lookup"><span data-stu-id="645f9-202"><a name="VDI_prereq"> </a></span></span>

<span data-ttu-id="645f9-203">當您在 VDI 環境中使用商務用 Skype 2015 用戶端時，已知的限制如下：</span><span class="sxs-lookup"><span data-stu-id="645f9-203">The following are known limitations when you use the Skype for Business 2015 client in a VDI environment:</span></span>
  
<span data-ttu-id="645f9-204">「呼叫委派」和「回應群組代理程式」匿名功能的支援有限。</span><span class="sxs-lookup"><span data-stu-id="645f9-204">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>
  
<span data-ttu-id="645f9-205">不支援以下功能：</span><span class="sxs-lookup"><span data-stu-id="645f9-205">There is no support for the following features:</span></span>
  
- <span data-ttu-id="645f9-206">整合式音訊裝置及視訊裝置調整頁面。</span><span class="sxs-lookup"><span data-stu-id="645f9-206">Integrated Audio Device and Video Device tuning pages.</span></span>
    
- <span data-ttu-id="645f9-207">多 view 影片。</span><span class="sxs-lookup"><span data-stu-id="645f9-207">Multiple-view video.</span></span>
    
- <span data-ttu-id="645f9-208">錄製交談。</span><span class="sxs-lookup"><span data-stu-id="645f9-208">Recording of conversations.</span></span>
    
- <span data-ttu-id="645f9-209">以匿名方式加入會議 (也就是說，加入由未與您) 組織建立同盟之組織所主控的商務用 Skype 會議。</span><span class="sxs-lookup"><span data-stu-id="645f9-209">Joining meetings anonymously (that is, joining Skype for Business meetings hosted by an organization that does not federate with your organization).</span></span>
    
- <span data-ttu-id="645f9-210">使用 Lync VDI 外掛程式和 Lync Phone Edition 裝置。</span><span class="sxs-lookup"><span data-stu-id="645f9-210">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
- <span data-ttu-id="645f9-211">在網路中斷連線的情況下延續通話。</span><span class="sxs-lookup"><span data-stu-id="645f9-211">Call continuity in case of a network outage.</span></span>
    
- <span data-ttu-id="645f9-212">自訂鈴聲和暫止的音樂功能。</span><span class="sxs-lookup"><span data-stu-id="645f9-212">Customized ringtones and music-on-hold features.</span></span>
    
<span data-ttu-id="645f9-213">Microsoft 365 或 Office 365 環境中不支援 Lync VDI 外掛程式。</span><span class="sxs-lookup"><span data-stu-id="645f9-213">The Lync VDI plug-in is not supported in Microsoft 365 or Office 365 environments.</span></span>
  
> [!NOTE]
> <span data-ttu-id="645f9-214">Citrix 即時優化套件支援 Microsoft 365 和 Office 365。</span><span class="sxs-lookup"><span data-stu-id="645f9-214">The Citrix RealTime Optimization Pack does support Microsoft 365 and Office 365.</span></span> <span data-ttu-id="645f9-215">針對 Citrix 型虛擬環境，請參閱 Citrix 的 [技術綜述](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) 檔，以取得支援的功能和版本清單。</span><span class="sxs-lookup"><span data-stu-id="645f9-215">For Citrix-based virtual environments, review Citrix's [Technical Overview](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) documentation for the list of supported features and versions.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="645f9-216">另請參閱</span><span class="sxs-lookup"><span data-stu-id="645f9-216">See also</span></span>
<span data-ttu-id="645f9-217"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="645f9-217"><a name="Citrix_RT"> </a></span></span>

[<span data-ttu-id="645f9-218">使用商務用 Skype Server 部署 Lync VDI 外掛程式</span><span class="sxs-lookup"><span data-stu-id="645f9-218">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

