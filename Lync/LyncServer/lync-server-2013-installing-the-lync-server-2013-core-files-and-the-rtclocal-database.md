---
title: 安裝 Lync Server 2013 core 檔案和 RTCLocal 資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99eccdd8d6473c25c6096c370f616975c7da141f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a><span data-ttu-id="38c0b-102">安裝 Lync Server 2013 core 檔案和 RTCLocal 資料庫</span><span class="sxs-lookup"><span data-stu-id="38c0b-102">Installing the Lync Server 2013 core files and the RTCLocal database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38c0b-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="38c0b-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="38c0b-104">若要在電腦上安裝 Lync Server 2013 core 檔案，請完成下列程式。</span><span class="sxs-lookup"><span data-stu-id="38c0b-104">To install the Lync Server 2013 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="38c0b-105">當您安裝核心檔案時，系統會自動安裝 RTCLocal 資料庫。</span><span class="sxs-lookup"><span data-stu-id="38c0b-105">The RTCLocal database is automatically installed when you install the core files.</span></span> <span data-ttu-id="38c0b-106">請注意，您不需要在觀察程式節點上安裝 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="38c0b-106">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="38c0b-107">相反地，系統會自動為您安裝 SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="38c0b-107">Instead, SQL Server Express is automatically installed for you.</span></span>

<span data-ttu-id="38c0b-108">若要安裝 Lync Server 2013 core 檔案和 RTCLocal 資料庫：</span><span class="sxs-lookup"><span data-stu-id="38c0b-108">To install the Lync Server 2013 core files and the RTCLocal database:</span></span>

1.  <span data-ttu-id="38c0b-109">在觀察程式節點電腦上，按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，以滑鼠右鍵按一下**命令提示**字元，然後按一下 [**以系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="38c0b-109">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="38c0b-110">在主控台視窗中，輸入下列命令，然後按 ENTER，使用適用于 Lync 伺服器設定檔案的路徑：</span><span class="sxs-lookup"><span data-stu-id="38c0b-110">In the console window, type the following command and then press ENTER, using the appropriate path to your Lync Server setup files:</span></span>
    
        D:\Setup.exe /BootstrapLocalMgmt

<span data-ttu-id="38c0b-111">若要確認已成功安裝核心 Lync 伺服器元件，請按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **lync server 2013**]，然後按一下 [ **lync server Management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="38c0b-111">To verify that the core Lync Server components were successfully installed, click **Start**, click **All Programs**, click **Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="38c0b-112">在 Lync Server 2013 管理命令介面中，輸入下列 Windows PowerShell 命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="38c0b-112">In the Lync Server 2013 Management Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="38c0b-113">當您第一次執行此命令時，系統不會傳回任何資料，因為您尚未設定任何觀察程式節點電腦。</span><span class="sxs-lookup"><span data-stu-id="38c0b-113">The first time you run this command, you no data is returned because you have not configured any watcher node computers yet.</span></span> <span data-ttu-id="38c0b-114">只要命令執行時不會傳回錯誤，您就可以假設 Lync Server 安裝程式已順利完成。</span><span class="sxs-lookup"><span data-stu-id="38c0b-114">As long as the command runs without returning an error, you can assume that the Lync Server setup completed successfully.</span></span>

<span data-ttu-id="38c0b-115">如果您的系統監控程式節點電腦位於周邊網路內，您可以執行下列命令以驗證 Lync Server 2013 的安裝：</span><span class="sxs-lookup"><span data-stu-id="38c0b-115">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Lync Server 2013:</span></span>

    Get-CsPinPolicy

<span data-ttu-id="38c0b-116">您會收到如下所示的資訊，視您在組織中設定使用的個人識別碼（PIN）原則而定：</span><span class="sxs-lookup"><span data-stu-id="38c0b-116">You will receive information similar to the following, depending on the number of personal identification number (PIN) policies configured for use in your organization:</span></span>

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

<span data-ttu-id="38c0b-117">如果您看到 PIN 原則的相關資訊，表示您已成功安裝核心元件。</span><span class="sxs-lookup"><span data-stu-id="38c0b-117">If you see information about your PIN policies, it means that you have successfully installed the core components.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

