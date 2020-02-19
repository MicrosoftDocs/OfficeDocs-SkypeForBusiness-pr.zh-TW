---
title: Lync Server 2013： 安裝 Operation Manager 代理程式檔案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7b658475e911d300d4ec8f6c15320e69ab71e15
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42118846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a><span data-ttu-id="5eec0-102">Lync Server 2013 中安裝 Operation Manager 代理程式檔案</span><span class="sxs-lookup"><span data-stu-id="5eec0-102">Installing the Operation Manager agent files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5eec0-103">_**主題上次修改日期：** 2012年-10-20 個_</span><span class="sxs-lookup"><span data-stu-id="5eec0-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="5eec0-104">若要安裝 Operations Manager 代理程式檔案的電腦上，完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="5eec0-104">To install the Operations Manager agent files on the computer, complete the following steps.</span></span>

1.  <span data-ttu-id="5eec0-105">在您的 System Center 安裝媒體上，按兩下**SetupOM.exe**。</span><span class="sxs-lookup"><span data-stu-id="5eec0-105">On your System Center setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="5eec0-106">在 System Center Operation Manager 安裝程式中，按一下 [**安裝 Operations Manager 代理程式**]。</span><span class="sxs-lookup"><span data-stu-id="5eec0-106">In System Center Operation Manager setup, click **Install Operations Manager Agent**.</span></span>

3.  <span data-ttu-id="5eec0-107">在 System Center 安裝精靈]**歡迎使用 System Center Operations Manager 安裝程式**精靈頁面上，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="5eec0-107">In System Center Setup wizard, on the **Welcome to the System Center Operations Manager Setup** wizard page, click **Next**.</span></span>

4.  <span data-ttu-id="5eec0-108">在 [**目的資料夾**] 頁面上，選取的資料夾位置的 Operations Manager 代理程式檔案將會安裝，然後按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="5eec0-108">On the **Destination Folder** page, select the folder where the Operations Manager Agent files will be installed, and then click **Next**.</span></span>

5.  <span data-ttu-id="5eec0-109">在 [**管理群組設定**] 頁面上，選取 [**指定管理群組資訊**]，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="5eec0-109">On the **Management Group Configuration** page, select **Specify Management Group information**, and then click **Next**.</span></span>

6.  <span data-ttu-id="5eec0-110">在 [**管理群組設定**] 頁面中**管理群組名稱**] 方塊中，輸入 [Operations Manager 管理群組的名稱，然後輸入您的 Operations Manager 伺服器的主機名稱 (例如，atl-cs-scom-001) 在 [**管理伺服器**] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="5eec0-110">On the **Management Group Configuration** page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="5eec0-111">如果您已變更 Operations Manager 所使用的連接埠號碼，然後在 [管理伺服器連接埠] 方塊中輸入新的連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="5eec0-111">If you have changed the port number used by Operations Manager, then type the new port number in the Management Server Port box.</span></span> <span data-ttu-id="5eec0-112">否則，保留在 5723 的預設值的連接埠，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="5eec0-112">Otherwise, leave the port at the default value of 5723 and click **Next**.</span></span>

7.  <span data-ttu-id="5eec0-113">在**代理程式動作帳戶**] 頁面上，選取 [**本機系統**]，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="5eec0-113">On the **Agent Action Account** page, select **Local System**, and then click **Next**.</span></span>

8.  <span data-ttu-id="5eec0-114">在**Microsoft Update** ] 頁面上，選取 [**我不想要使用 Microsoft Update**，然後再按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="5eec0-114">On the **Microsoft Update** page, select **I don't want to use Microsoft Update**, and then click **Next**.</span></span>

9.  <span data-ttu-id="5eec0-115">在**安裝準備就緒]** 頁面上，按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="5eec0-115">On the **Ready to Install** page, click **Install**.</span></span>

10. <span data-ttu-id="5eec0-116">在 [**正在完成 System Center Operations Manager 安裝精靈**] 頁面上，按一下 [**完成]**。</span><span class="sxs-lookup"><span data-stu-id="5eec0-116">On the **Completing the System Center Operations Manager Setup wizard** page, click **Finish**.</span></span>

11. <span data-ttu-id="5eec0-117">按一下 **[結束]**。</span><span class="sxs-lookup"><span data-stu-id="5eec0-117">Click **Exit**.</span></span>

<span data-ttu-id="5eec0-118">如果您使用 System Center 2007 R2，您可以驗證代理程式已經建立的依序按一下 [**開始**、 [**所有程式]**、 [ **System Center Operations Manager 2007 R2**，然後按一下 [ **Operations Manager 殼層**。</span><span class="sxs-lookup"><span data-stu-id="5eec0-118">If you are using System Center 2007 R2, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2007 R2**, and then clicking **Operations Manager Shell**.</span></span> <span data-ttu-id="5eec0-119">在 Operations Manager 介面中，輸入下列 Windows PowerShell 命令，並按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="5eec0-119">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-Agent 

<span data-ttu-id="5eec0-120">所有 Operations Manager 代理程式的清單會出現在螢幕上。</span><span class="sxs-lookup"><span data-stu-id="5eec0-120">A list of all your Operations Manager agents will appear onscreen.</span></span>

<span data-ttu-id="5eec0-121">如果您使用 System Center 2012，請從 Operations 2012 Manager 殼層執行此命令：</span><span class="sxs-lookup"><span data-stu-id="5eec0-121">If you are using System Center 2012, run this command from the Operations 2012 Manager Shell:</span></span>

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

