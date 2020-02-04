---
title: Lync Server 2013：檢查最佳做法分析程式的更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking for updates to Best Practices Analyzer
ms:assetid: 06f1da8b-99a7-4871-911e-bfb7542baced
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204645(v=OCS.15)
ms:contentKeyID: 48183307
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffd05761a1c107ac72c7b9c3242fb18a5a3c7a27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-for-updates-to-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="2f5f6-102">在 Lync Server 2013 中檢查最佳做法分析程式的更新</span><span class="sxs-lookup"><span data-stu-id="2f5f6-102">Checking for updates to Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f5f6-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2f5f6-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2f5f6-104">當您啟動最佳做法分析程式時，工具會提供一個選項，讓您搜尋工具的最新更新。</span><span class="sxs-lookup"><span data-stu-id="2f5f6-104">When you start Best Practices Analyzer, the tool provides you with an option to search for the latest updates to the tool.</span></span> <span data-ttu-id="2f5f6-105">如果有可用的更新，您可以下載更新。</span><span class="sxs-lookup"><span data-stu-id="2f5f6-105">If an update is available, you can download the update.</span></span> <span data-ttu-id="2f5f6-106">如果您選擇不下載更新，或最佳做法分析程式無法存取網際網路，您可以繼續使用電腦上已經存在的版本。</span><span class="sxs-lookup"><span data-stu-id="2f5f6-106">If you choose not to download updates, or if Best Practices Analyzer cannot access the Internet, you can continue to use the version that is already on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2f5f6-107">如果您需要 proxy 驗證才能存取網際網路，最佳做法分析程式無法存取您要下載的新更新。</span><span class="sxs-lookup"><span data-stu-id="2f5f6-107">If you need proxy authentication to access the Internet, Best Practices Analyzer cannot access new updates for you to download.</span></span> <span data-ttu-id="2f5f6-108">不過，您可以從 Microsoft 下載中心手動下載最新版本的 RtcBPA <A href="http://go.microsoft.com/fwlink/p/?linkid=266539">http://go.microsoft.com/fwlink/p/?linkId=266539</A>。</span><span class="sxs-lookup"><span data-stu-id="2f5f6-108">However, you can manually download the latest version of RtcBPA.msi from the Microsoft Download Center at <A href="http://go.microsoft.com/fwlink/p/?linkid=266539">http://go.microsoft.com/fwlink/p/?linkId=266539</A>.</span></span> <span data-ttu-id="2f5f6-109">下載檔案之後，您可以將檔案複製到您想要更新最佳做法分析程式的電腦上，並使用 .msi 檔案在該電腦上安裝新版工具。</span><span class="sxs-lookup"><span data-stu-id="2f5f6-109">After downloading the file, you can copy it to the computer on which you want to update Best Practices Analyzer and use the .msi file to install the new version of the tool on that computer.</span></span>



</div>

<span data-ttu-id="2f5f6-110">若要更新最佳做法分析程式規則，您必須在本機電腦上以系統管理員身分執行該工具。</span><span class="sxs-lookup"><span data-stu-id="2f5f6-110">To update Best Practices Analyzer rules, you must run the tool as an Administrator on the local computer.</span></span> <span data-ttu-id="2f5f6-111">如果您未使用系統管理員群組成員的帳戶登入，且偵測到更新，請關閉最佳做法分析程式，然後使用下列程式來啟動程式。</span><span class="sxs-lookup"><span data-stu-id="2f5f6-111">If you are not logged on using an account that is a member of the Administrators group and updates are detected, close Best Practices Analyzer, and then use the following procedure to start the program.</span></span>

<div>

## <a name="to-open-best-practices-analyzer-as-administrator-to-check-for-updates"></a><span data-ttu-id="2f5f6-112">若要以系統管理員身分開啟最佳做法分析程式來檢查更新</span><span class="sxs-lookup"><span data-stu-id="2f5f6-112">To open Best Practices Analyzer as Administrator to check for updates</span></span>

1.  <span data-ttu-id="2f5f6-113">在已安裝最佳做法分析程式的電腦上，按一下 [**開始**]，指向 [ **Microsoft Lync Server 2013**]，以滑鼠右鍵按一下 [**最佳做法分析**程式]，然後按一下 [**以系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="2f5f6-113">On a computer on which Best Practices Analyzer is installed, click **Start**, point to **Microsoft Lync Server 2013**, right-click **Best Practices Analyzer**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="2f5f6-114">指定屬於 [管理員] 群組成員的帳號憑證。</span><span class="sxs-lookup"><span data-stu-id="2f5f6-114">Specify credentials of an account that is a member of the Administrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

