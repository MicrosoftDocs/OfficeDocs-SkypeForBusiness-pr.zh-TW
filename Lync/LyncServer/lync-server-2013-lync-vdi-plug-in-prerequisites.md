---
title: Lync Server 2013： Lync VDI 外掛程式必要條件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b63ee7f494b131fc194d6bf9d028525efd71cf0a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534680"
---
# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a><span data-ttu-id="9c876-102">Lync Server 2013 中的 lync VDI 外掛程式必要條件</span><span class="sxs-lookup"><span data-stu-id="9c876-102">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c876-103">_**主題上次修改日期：** 2017-03-07_</span><span class="sxs-lookup"><span data-stu-id="9c876-103">_**Topic Last Modified:** 2017-03-07_</span></span>

<span data-ttu-id="9c876-104">在虛擬桌面基礎結構 (VDI) 環境中，虛擬機器和使用者的本機電腦必須符合本節所述的需求。</span><span class="sxs-lookup"><span data-stu-id="9c876-104">In a virtual desktop infrastructure (VDI) environment, the virtual machines and the user’s local computer must meet the requirements outlined in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9c876-105">如需如何安裝及部署虛擬化環境的詳細資訊，請參閱您的虛擬化解決方案供應商。</span><span class="sxs-lookup"><span data-stu-id="9c876-105">Refer to your virtualization solution provider for details about how to install and deploy the virtualized environment.</span></span> <span data-ttu-id="9c876-106">如需根據 Hyper-V 和遠端桌面服務部署虛擬化環境的詳細資訊，請參閱 Microsoft TechNet 程式庫中的下列文章：</span><span class="sxs-lookup"><span data-stu-id="9c876-106">For information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft TechNet Library:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="9c876-107">Hyper-V <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span><span class="sxs-lookup"><span data-stu-id="9c876-107">Hyper-V at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span></span></P>
> <LI>
> <P><span data-ttu-id="9c876-108">Windows Server &nbsp; 2008 R2 的遠端桌面 &nbsp; 服務 <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span><span class="sxs-lookup"><span data-stu-id="9c876-108">Remote Desktop Services in Windows Server&nbsp;2008&nbsp;R2 at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="9c876-109">下列為在資料中心電腦上執行的虛擬機器的需求。</span><span class="sxs-lookup"><span data-stu-id="9c876-109">The following are requirements for the virtual machines running on the data center computer:</span></span>

  - <span data-ttu-id="9c876-110">虛擬機器必須設定 Windows 10、Windows 8.1、Windows 8、Windows 7 或 Windows Server 2008 R2 搭配最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="9c876-110">Virtual machines must be configured with Windows 10, Windows 8.1, Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>

<span data-ttu-id="9c876-111">以下是使用者和使用者的本機電腦需求：</span><span class="sxs-lookup"><span data-stu-id="9c876-111">The following are requirements for the user and the user’s local computer:</span></span>

  - <span data-ttu-id="9c876-112">使用者必須駐留在 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="9c876-112">The user must be homed on Lync Server 2013.</span></span>

  - <span data-ttu-id="9c876-113">本機電腦必須執行 Windows Embedded Standard 7 與 SP1、Windows 7 搭配 SP1、Windows 8、Windows 8.1 Embedded 或 Windows 8.1 (非內嵌式) 。</span><span class="sxs-lookup"><span data-stu-id="9c876-113">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, Windows 8, Windows 8.1 Embedded, or Windows 8.1 (not embedded).</span></span>

  - <span data-ttu-id="9c876-114">如果您使用的是遠端桌面服務，Lync VDI 外掛程式位數 (也就是說，該應用程式是否為32位或64位) 必須符合本機電腦的作業系統位數。</span><span class="sxs-lookup"><span data-stu-id="9c876-114">If you are using Remote Desktop Services, the Lync VDI plug-in bitness (that is, whether the application is 32-bit or 64-bit) must match the local computer’s operating system bitness.</span></span> <span data-ttu-id="9c876-115">本機電腦上的作業系統和虛擬機器上的作業系統的位數不需要相符。</span><span class="sxs-lookup"><span data-stu-id="9c876-115">The bitness of the operating system on the local computer and the operating system on the virtual machine do not need to match.</span></span> <span data-ttu-id="9c876-116">如果您使用其他虛擬化解決方案或平臺，請參閱虛擬化解決方案供應商關於位數需求的指導方針。</span><span class="sxs-lookup"><span data-stu-id="9c876-116">If you are using another virtualization solution or platform, refer to guidance from your virtualization solution provider about bitness requirements.</span></span>

  - <span data-ttu-id="9c876-117">本機電腦必須執行最新版本的遠端桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="9c876-117">The local computer must be running the latest version of the remote desktop client.</span></span> <span data-ttu-id="9c876-118">從 Microsoft 或您的虛擬化解決方案供應商，安裝遠端桌面服務用戶端的最新更新（或最新的遠端桌面用戶端軟體）。</span><span class="sxs-lookup"><span data-stu-id="9c876-118">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> <span data-ttu-id="9c876-119">如需最新的遠端桌面服務更新，請參閱 [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) 。</span><span class="sxs-lookup"><span data-stu-id="9c876-119">For the latest Remote Desktop Services updates, see [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

  - <span data-ttu-id="9c876-120">在本機電腦上，必須設定遠端桌面用戶端設定，以便在本機電腦上播放音訊，並停用遠端錄製。</span><span class="sxs-lookup"><span data-stu-id="9c876-120">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="9c876-121">若要在 Windows 中為遠端桌面連線設定這些設定，請參閱下一節「設定遠端桌面連線設定」。</span><span class="sxs-lookup"><span data-stu-id="9c876-121">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span>

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a><span data-ttu-id="9c876-122">設定遠端桌面連線設定</span><span class="sxs-lookup"><span data-stu-id="9c876-122">To configure Remote Desktop Connection settings</span></span>

<span data-ttu-id="9c876-123">若要在 Windows 中為 Lync VDI 外掛程式準備遠端桌面連線，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="9c876-123">To prepare Remote Desktop Connection in Windows for the Lync VDI plug-in, follow these steps.</span></span>

1.  <span data-ttu-id="9c876-124">如果本機電腦正在執行 Windows 8，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="9c876-124">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="9c876-125">如果本機電腦執行的是 Windows 7 與 SP1，請安裝最新的 Windows 8 版本的遠端桌面服務用戶端，網址為 [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) 。</span><span class="sxs-lookup"><span data-stu-id="9c876-125">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the Remote Desktop Services client, available at [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

2.  <span data-ttu-id="9c876-126">按一下 [ **開始**]，然後按一下 [ **遠端桌面**連線]，以啟動遠端桌面服務用戶端。</span><span class="sxs-lookup"><span data-stu-id="9c876-126">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>

3.  <span data-ttu-id="9c876-127">按一下 **[選項]**。</span><span class="sxs-lookup"><span data-stu-id="9c876-127">Click **Options**.</span></span>

4.  <span data-ttu-id="9c876-128">按一下 [ **本機資源** ] 索引標籤。在 [ **遠端音訊**] 底下，按一下 [ **設定**]，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="9c876-128">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
      - <span data-ttu-id="9c876-129">在 [ **遠端音訊播放**] 底下，選取 [ **在此電腦上播放**]。</span><span class="sxs-lookup"><span data-stu-id="9c876-129">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
      - <span data-ttu-id="9c876-130">在 [ **遠端音訊錄製**] 底下，選取 [不 **錄製**]。</span><span class="sxs-lookup"><span data-stu-id="9c876-130">Under **Remote audio recording**, select **Do not record**.</span></span>
    
      - <span data-ttu-id="9c876-131">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c876-131">Click **OK**.</span></span>

5.  <span data-ttu-id="9c876-132">按一下 [ **體驗** ] 索引標籤。在 [ **效能**] 下，清除 [ **持續性點陣圖** 快取] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="9c876-132">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>

6.  <span data-ttu-id="9c876-133">按一下 [ **一般** ] 索引標籤。在 [ **電腦**] 中，輸入虛擬機器的名稱，然後按一下 **[連接]**。</span><span class="sxs-lookup"><span data-stu-id="9c876-133">Click the **General** tab. In **Computer**, type the name of the virtual machine, and then click **Connect**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

