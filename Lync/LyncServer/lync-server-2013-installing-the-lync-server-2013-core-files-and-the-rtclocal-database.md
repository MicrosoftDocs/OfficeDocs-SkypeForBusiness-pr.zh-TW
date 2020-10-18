---
title: 安裝 Lync Server 2013 核心檔案與 RTCLocal 資料庫
description: 安裝 Lync Server 2013 核心檔案和 RTCLocal 資料庫。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68964f8b80f6377afd859d113783d61e33afbebd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573859"
---
# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a><span data-ttu-id="6f98c-103">安裝 Lync Server 2013 核心檔案與 RTCLocal 資料庫</span><span class="sxs-lookup"><span data-stu-id="6f98c-103">Installing the Lync Server 2013 core files and the RTCLocal database</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f98c-104">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="6f98c-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="6f98c-105">若要在電腦上安裝 Lync Server 2013 核心檔案，請完成下列程式。</span><span class="sxs-lookup"><span data-stu-id="6f98c-105">To install the Lync Server 2013 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="6f98c-106">當您安裝核心檔案時，會自動安裝 RTCLocal 資料庫。</span><span class="sxs-lookup"><span data-stu-id="6f98c-106">The RTCLocal database is automatically installed when you install the core files.</span></span> <span data-ttu-id="6f98c-107">請注意，您不需要在觀察程式節點上安裝 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="6f98c-107">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="6f98c-108">相反地，系統會自動為您安裝 SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="6f98c-108">Instead, SQL Server Express is automatically installed for you.</span></span>

<span data-ttu-id="6f98c-109">若要安裝 Lync Server 2013 核心檔案和 RTCLocal 資料庫：</span><span class="sxs-lookup"><span data-stu-id="6f98c-109">To install the Lync Server 2013 core files and the RTCLocal database:</span></span>

1.  <span data-ttu-id="6f98c-110">在監看員節點電腦上，依序按一下 [ **開始**]、[ **所有程式**]、[ **附件**]、滑鼠右鍵按一下 [ **命令提示**字元] 及 [以 **系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="6f98c-110">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="6f98c-111">在主控台視窗中，輸入下列命令，然後按 ENTER，使用 Lync Server 安裝盤的適當路徑：</span><span class="sxs-lookup"><span data-stu-id="6f98c-111">In the console window, type the following command and then press ENTER, using the appropriate path to your Lync Server setup files:</span></span>
    
        D:\Setup.exe /BootstrapLocalMgmt

<span data-ttu-id="6f98c-112">若要驗證是否已成功安裝核心 Lync Server 元件，請依序按一下 [ **開始**]、[ **所有程式**]、[ **lync server 2013**]，然後按一下 [ **lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="6f98c-112">To verify that the core Lync Server components were successfully installed, click **Start**, click **All Programs**, click **Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="6f98c-113">在 [Lync Server 2013 管理命令介面] 中，輸入下列 Windows PowerShell 命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="6f98c-113">In the Lync Server 2013 Management Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="6f98c-114">當您第一次執行此命令時，您不會傳回任何資料，因為您尚未設定任何監視節點電腦。</span><span class="sxs-lookup"><span data-stu-id="6f98c-114">The first time you run this command, you no data is returned because you have not configured any watcher node computers yet.</span></span> <span data-ttu-id="6f98c-115">只要命令執行但未傳回錯誤，您就可以假設 Lync Server 安裝程式已順利完成。</span><span class="sxs-lookup"><span data-stu-id="6f98c-115">As long as the command runs without returning an error, you can assume that the Lync Server setup completed successfully.</span></span>

<span data-ttu-id="6f98c-116">如果您的監看員節點電腦位於周邊網路內，您可以執行下列命令來驗證 Lync Server 2013 的安裝：</span><span class="sxs-lookup"><span data-stu-id="6f98c-116">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Lync Server 2013:</span></span>

    Get-CsPinPolicy

<span data-ttu-id="6f98c-117">根據您在組織中設定供使用的個人識別碼 (PIN) 原則，您會收到與下列類似的資訊：</span><span class="sxs-lookup"><span data-stu-id="6f98c-117">You will receive information similar to the following, depending on the number of personal identification number (PIN) policies configured for use in your organization:</span></span>

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

<span data-ttu-id="6f98c-118">如果您看到 PIN 原則的相關資訊，這表示您已成功安裝核心元件。</span><span class="sxs-lookup"><span data-stu-id="6f98c-118">If you see information about your PIN policies, it means that you have successfully installed the core components.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

