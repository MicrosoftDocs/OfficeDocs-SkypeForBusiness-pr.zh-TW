---
title: Lync Server 2013：Lync VDI 外掛程式先決條件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae32480e5a3dbfbdfc22c4dbde59c62383c9587f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a><span data-ttu-id="54d24-102">Lync Server 2013 中的 Lync VDI 外掛程式先決條件</span><span class="sxs-lookup"><span data-stu-id="54d24-102">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54d24-103">_**主題上次修改日期：** 2017-03-07_</span><span class="sxs-lookup"><span data-stu-id="54d24-103">_**Topic Last Modified:** 2017-03-07_</span></span>

<span data-ttu-id="54d24-104">在虛擬桌面基礎結構（VDI）環境中，虛擬機器與使用者的本機電腦必須符合本節中所述的需求。</span><span class="sxs-lookup"><span data-stu-id="54d24-104">In a virtual desktop infrastructure (VDI) environment, the virtual machines and the user’s local computer must meet the requirements outlined in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="54d24-105">如需有關如何安裝及部署虛擬化環境的詳細資訊，請參閱您的虛擬化解決方案提供者。</span><span class="sxs-lookup"><span data-stu-id="54d24-105">Refer to your virtualization solution provider for details about how to install and deploy the virtualized environment.</span></span> <span data-ttu-id="54d24-106">如需有關根據 Hyper-v 和遠端桌面服務部署虛擬化環境的相關資訊，請參閱 Microsoft TechNet 文件庫中的下列文章：</span><span class="sxs-lookup"><span data-stu-id="54d24-106">For information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft TechNet Library:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="54d24-107">Hyper-v<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span><span class="sxs-lookup"><span data-stu-id="54d24-107">Hyper-V at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span></span></P>
> <LI>
> <P><span data-ttu-id="54d24-108">Windows Server&nbsp;2008&nbsp;R2 中的遠端桌面服務<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span><span class="sxs-lookup"><span data-stu-id="54d24-108">Remote Desktop Services in Windows Server&nbsp;2008&nbsp;R2 at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="54d24-109">下列是在資料中心電腦上執行的虛擬機器需求：</span><span class="sxs-lookup"><span data-stu-id="54d24-109">The following are requirements for the virtual machines running on the data center computer:</span></span>

  - <span data-ttu-id="54d24-110">虛擬機器必須使用 Windows 10、Windows 8.1、Windows 8、Windows 7 或 Windows Server 2008 R2 （含最新的 service pack）進行設定。</span><span class="sxs-lookup"><span data-stu-id="54d24-110">Virtual machines must be configured with Windows 10, Windows 8.1, Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>

<span data-ttu-id="54d24-111">以下是使用者與使用者的本機電腦需求：</span><span class="sxs-lookup"><span data-stu-id="54d24-111">The following are requirements for the user and the user’s local computer:</span></span>

  - <span data-ttu-id="54d24-112">使用者必須駐留在 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="54d24-112">The user must be homed on Lync Server 2013.</span></span>

  - <span data-ttu-id="54d24-113">本機電腦必須執行 Windows Embedded Standard 7 （含 SP1）、Windows 7 （含 SP1）、windows 8、Windows 8.1 Embedded 或 Windows 8.1 （未內嵌）。</span><span class="sxs-lookup"><span data-stu-id="54d24-113">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, Windows 8, Windows 8.1 Embedded, or Windows 8.1 (not embedded).</span></span>

  - <span data-ttu-id="54d24-114">如果您使用的是遠端桌面服務，Lync VDI 外掛程式位數（也就是應用程式是32位或64位）必須符合本機電腦的作業系統位數。</span><span class="sxs-lookup"><span data-stu-id="54d24-114">If you are using Remote Desktop Services, the Lync VDI plug-in bitness (that is, whether the application is 32-bit or 64-bit) must match the local computer’s operating system bitness.</span></span> <span data-ttu-id="54d24-115">本機電腦上的作業系統與虛擬機器上作業系統的位數不需要相符。</span><span class="sxs-lookup"><span data-stu-id="54d24-115">The bitness of the operating system on the local computer and the operating system on the virtual machine do not need to match.</span></span> <span data-ttu-id="54d24-116">如果您使用的是其他虛擬化解決方案或平臺，請參閱虛擬化解決方案供應商關於位數需求的指導方針。</span><span class="sxs-lookup"><span data-stu-id="54d24-116">If you are using another virtualization solution or platform, refer to guidance from your virtualization solution provider about bitness requirements.</span></span>

  - <span data-ttu-id="54d24-117">本機電腦必須執行最新版本的遠端桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="54d24-117">The local computer must be running the latest version of the remote desktop client.</span></span> <span data-ttu-id="54d24-118">從您的虛擬化方案提供者，從 Microsoft 或最新的遠端桌面用戶端軟體，安裝遠端桌面服務用戶端的最新更新。</span><span class="sxs-lookup"><span data-stu-id="54d24-118">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> <span data-ttu-id="54d24-119">如需最新的遠端桌面服務更新[https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)，請參閱。</span><span class="sxs-lookup"><span data-stu-id="54d24-119">For the latest Remote Desktop Services updates, see [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

  - <span data-ttu-id="54d24-120">在本機電腦上，必須設定遠端桌面用戶端設定，以便在本機電腦上播放音訊，並停用遠端錄製。</span><span class="sxs-lookup"><span data-stu-id="54d24-120">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="54d24-121">若要在 Windows 中設定遠端桌面連線的這些設定，請參閱下一節「設定遠端桌面連線設定」。</span><span class="sxs-lookup"><span data-stu-id="54d24-121">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span>

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a><span data-ttu-id="54d24-122">設定遠端桌面連線設定</span><span class="sxs-lookup"><span data-stu-id="54d24-122">To configure Remote Desktop Connection settings</span></span>

<span data-ttu-id="54d24-123">若要在 Windows 中為 Lync VDI 外掛程式準備遠端桌面連線，請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="54d24-123">To prepare Remote Desktop Connection in Windows for the Lync VDI plug-in, follow these steps.</span></span>

1.  <span data-ttu-id="54d24-124">如果本機電腦執行的是 Windows 8，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="54d24-124">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="54d24-125">如果本機電腦執行的是 Windows 7 與 SP1，請安裝最新的 Windows 8 版的遠端桌面服務用戶端， [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)網址為。</span><span class="sxs-lookup"><span data-stu-id="54d24-125">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the Remote Desktop Services client, available at [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

2.  <span data-ttu-id="54d24-126">按一下 [**開始**]，然後按一下 [**遠端桌面**連線]，啟動遠端桌面服務用戶端。</span><span class="sxs-lookup"><span data-stu-id="54d24-126">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>

3.  <span data-ttu-id="54d24-127">按一下 [**選項**]。</span><span class="sxs-lookup"><span data-stu-id="54d24-127">Click **Options**.</span></span>

4.  <span data-ttu-id="54d24-128">按一下 [**本機資源**] 索引標籤。在 [**遠端音訊**] 底下，按一下 [**設定**]，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="54d24-128">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
      - <span data-ttu-id="54d24-129">在 [**遠端音訊播放**] 底下，選取 [**在這台電腦上播放**]。</span><span class="sxs-lookup"><span data-stu-id="54d24-129">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
      - <span data-ttu-id="54d24-130">在 [**遠端音訊錄製**] 底下，選取 [不**錄製**]。</span><span class="sxs-lookup"><span data-stu-id="54d24-130">Under **Remote audio recording**, select **Do not record**.</span></span>
    
      - <span data-ttu-id="54d24-131">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54d24-131">Click **OK**.</span></span>

5.  <span data-ttu-id="54d24-132">按一下 [**體驗**] 索引標籤。在 [**效能**] 底下，清除 [**永久點陣圖緩存**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="54d24-132">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>

6.  <span data-ttu-id="54d24-133">按一下 [**一般**] 索引標籤。在 [**電腦**] 中，輸入虛擬機器的名稱，然後按一下 **[連線]**。</span><span class="sxs-lookup"><span data-stu-id="54d24-133">Click the **General** tab. In **Computer**, type the name of the virtual machine, and then click **Connect**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

