---
title: Lync Server 2013：安裝 Operation Manager 代理程式檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb8675e6c75c288e6594e45ecdcc2f65497a047a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a><span data-ttu-id="8587b-102">在 Lync Server 2013 中安裝 Operation Manager 代理程式檔</span><span class="sxs-lookup"><span data-stu-id="8587b-102">Installing the Operation Manager agent files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8587b-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="8587b-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="8587b-104">若要在電腦上安裝 Operations Manager 代理檔案，請完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="8587b-104">To install the Operations Manager agent files on the computer, complete the following steps.</span></span>

1.  <span data-ttu-id="8587b-105">在系統中心設定媒體上，按兩下 [ **SetupOM**]。</span><span class="sxs-lookup"><span data-stu-id="8587b-105">On your System Center setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="8587b-106">在 System Center Operation Manager 設定中，按一下 [**安裝 Operations Manager 代理**程式]。</span><span class="sxs-lookup"><span data-stu-id="8587b-106">In System Center Operation Manager setup, click **Install Operations Manager Agent**.</span></span>

3.  <span data-ttu-id="8587b-107">在 System Center 設定向導中，在 [**歡迎使用 System Center Operations Manager 安裝程式**嚮導] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8587b-107">In System Center Setup wizard, on the **Welcome to the System Center Operations Manager Setup** wizard page, click **Next**.</span></span>

4.  <span data-ttu-id="8587b-108">在 [**目的地資料夾**] 頁面上，選取將安裝 Operations Manager 代理程式檔案的資料夾，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8587b-108">On the **Destination Folder** page, select the folder where the Operations Manager Agent files will be installed, and then click **Next**.</span></span>

5.  <span data-ttu-id="8587b-109">在 [**管理群組**設定] 頁面上，選取 [**指定管理群組資訊**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8587b-109">On the **Management Group Configuration** page, select **Specify Management Group information**, and then click **Next**.</span></span>

6.  <span data-ttu-id="8587b-110">在 [**管理群組**設定] 頁面上，于 [**管理群組名稱**] 方塊中輸入 operations manager 管理群組的名稱，然後在 [**管理伺服器**] 方塊中輸入 operations manager 伺服器的主機名稱（例如 [atl-scom-001]）。</span><span class="sxs-lookup"><span data-stu-id="8587b-110">On the **Management Group Configuration** page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="8587b-111">如果您已經變更了 Operations Manager 所使用的埠號，請在 [管理伺服器埠] 方塊中輸入新的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="8587b-111">If you have changed the port number used by Operations Manager, then type the new port number in the Management Server Port box.</span></span> <span data-ttu-id="8587b-112">否則，請將埠保留為預設值5723，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8587b-112">Otherwise, leave the port at the default value of 5723 and click **Next**.</span></span>

7.  <span data-ttu-id="8587b-113">在 [**代理程式動作帳戶**] 頁面上，選取 [**本機系統**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8587b-113">On the **Agent Action Account** page, select **Local System**, and then click **Next**.</span></span>

8.  <span data-ttu-id="8587b-114">在 [ **Microsoft update** ] 頁面上，選取 [**我不想使用 Microsoft update**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8587b-114">On the **Microsoft Update** page, select **I don't want to use Microsoft Update**, and then click **Next**.</span></span>

9.  <span data-ttu-id="8587b-115">在 [**準備安裝**] 頁面上，按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="8587b-115">On the **Ready to Install** page, click **Install**.</span></span>

10. <span data-ttu-id="8587b-116">在 [**完成 System Center Operations Manager 安裝程式嚮導]** 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="8587b-116">On the **Completing the System Center Operations Manager Setup wizard** page, click **Finish**.</span></span>

11. <span data-ttu-id="8587b-117">按一下 **[** 結束]。</span><span class="sxs-lookup"><span data-stu-id="8587b-117">Click **Exit**.</span></span>

<span data-ttu-id="8587b-118">如果您使用的是 System Center 2007 R2，您可以按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **System Center Operations Manager 2007 R2**]，然後按一下 [ **Operations Manager Shell**]，確認已建立代理程式。</span><span class="sxs-lookup"><span data-stu-id="8587b-118">If you are using System Center 2007 R2, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2007 R2**, and then clicking **Operations Manager Shell**.</span></span> <span data-ttu-id="8587b-119">在 Operations Manager Shell 中，輸入下列 Windows PowerShell 命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="8587b-119">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-Agent 

<span data-ttu-id="8587b-120">系統會在螢幕上顯示所有 Operations Manager 代理程式的清單。</span><span class="sxs-lookup"><span data-stu-id="8587b-120">A list of all your Operations Manager agents will appear onscreen.</span></span>

<span data-ttu-id="8587b-121">如果您使用的是系統中心2012，請在 Operations 2012 管理器 Shell 中執行此命令：</span><span class="sxs-lookup"><span data-stu-id="8587b-121">If you are using System Center 2012, run this command from the Operations 2012 Manager Shell:</span></span>

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

