---
title: Lync Server 2013： 安裝 Lync Server 伺服器元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8f15afbb1602f369a063826c2196387dcff819b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a><span data-ttu-id="4bc64-102">安裝 Lync Server 2013 的伺服器元件</span><span class="sxs-lookup"><span data-stu-id="4bc64-102">Install server components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bc64-103">_**上次修改主題：** 2014年-05-05_</span><span class="sxs-lookup"><span data-stu-id="4bc64-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="4bc64-104">執行下列步驟之前，請確定您登入網域使用者帳戶是本機系統管理員和 Active Directory 中的 RTCUniversalReadOnlyAdmins 群組成員的伺服器。</span><span class="sxs-lookup"><span data-stu-id="4bc64-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmins group in Active Directory.</span></span>

<span data-ttu-id="4bc64-105">Lync Server 部署精靈用來安裝每個 Lync 伺服器角色的必要的元件以及啟動伺服器。</span><span class="sxs-lookup"><span data-stu-id="4bc64-105">The Lync Server Deployment Wizard is used to install the needed components for each Lync server role and to activate the server.</span></span> <span data-ttu-id="4bc64-106">本文會引導您完成部署 Standard Edition server 或前端伺服器 Lync 基礎結構中的步驟。</span><span class="sxs-lookup"><span data-stu-id="4bc64-106">This article walks you through the steps of deploying a Standard Edition server or a Front End Server in your Lync infrastructure.</span></span>

<div>

## <a name="to-install-lync-server-components"></a><span data-ttu-id="4bc64-107">安裝 Lync Server 元件</span><span class="sxs-lookup"><span data-stu-id="4bc64-107">To install Lync Server components</span></span>

1.  <span data-ttu-id="4bc64-108">如果未執行 Lync Server 部署精靈，請在您想要安裝到 Lync 伺服器上啟動它。</span><span class="sxs-lookup"><span data-stu-id="4bc64-108">If the Lync Server Deployment Wizard isn’t running, start it on the server you want to install Lync onto.</span></span>

2.  <span data-ttu-id="4bc64-109">按一下 [**安裝或更新 Lync Server 系統**]。</span><span class="sxs-lookup"><span data-stu-id="4bc64-109">Click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="4bc64-110">在 [部署精靈]，確認**步驟 1： 安裝本機設定存放區**有綠色核取記號，表示此伺服器皆已成功安裝的存放區的本機複本。</span><span class="sxs-lookup"><span data-stu-id="4bc64-110">In the Deployment Wizard, confirm that **Step 1: Install Local Configuration Store** has a green check mark, which means that this server has a local copy of the store installed successfully.</span></span> <span data-ttu-id="4bc64-111">如果未核取，您需要在伺服器上安裝本機設定存放區。</span><span class="sxs-lookup"><span data-stu-id="4bc64-111">If it’s not checked, you need to install the Local Configuration store on the server.</span></span> <span data-ttu-id="4bc64-112">遵循在[安裝本機設定存放區 Lync Server 2013 中](lync-server-2013-install-the-local-configuration-store.md)的步驟，然後再回來。</span><span class="sxs-lookup"><span data-stu-id="4bc64-112">Follow the steps at [Install the Local Configuration store in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) and then come back here.</span></span>

4.  <span data-ttu-id="4bc64-113">當您準備好您的伺服器上安裝 Lync Server 2013 元件時，請按一下 [**執行**下一步] 為**步驟 2： 安裝或移除 Lync Server 元件**。</span><span class="sxs-lookup"><span data-stu-id="4bc64-113">When you’re ready to install the Lync Server 2013 components on your server, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

5.  <span data-ttu-id="4bc64-114">在 [**設定設定 Lync Server 元件**] 頁面上，按 [**下一步**設定元件，如已發行的拓撲中所定義。</span><span class="sxs-lookup"><span data-stu-id="4bc64-114">On the **Set Up Lync Server Components** page, click **Next** to set up components as defined in your published topology.</span></span>

6.  <span data-ttu-id="4bc64-115">[**執行命令**] 頁面上會顯示命令和安裝資訊的摘要作為進行設定。</span><span class="sxs-lookup"><span data-stu-id="4bc64-115">The **Executing Commands** page will display a summary of commands and installation information as the set up takes place.</span></span> <span data-ttu-id="4bc64-116">完成後，您可以使用清單選取 [記錄] 來檢視，，，然後按一下 [**檢視記錄檔**。</span><span class="sxs-lookup"><span data-stu-id="4bc64-116">When it’s done, you can use the list to select a log to view, and then click **View Log**.</span></span>

7.  <span data-ttu-id="4bc64-117">Lync Server 2013 元件安裝完成時，且您已檢閱記錄檔，視需要請按一下 [**完成**] 以完成安裝在此步驟。</span><span class="sxs-lookup"><span data-stu-id="4bc64-117">When Lync Server 2013 components setup is done, and you’ve reviewed the logs as needed, click **Finish** to complete this step in the installation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4bc64-118">如果系統提示您重新啟動伺服器 （如果安裝所需的 Windows 桌面體驗，則可能發生），明確地這麼做。</span><span class="sxs-lookup"><span data-stu-id="4bc64-118">If you’re prompted to restart the server (which might happen if Windows Desktop Experience needed to be installed), definitely do that.</span></span> <span data-ttu-id="4bc64-119">在電腦上一步是啟動並執行，您需要透過一次，請執行下列步驟從步驟 3 上列 (基本上執行步驟 2 中部署精靈一個更多時間) 開始。</span><span class="sxs-lookup"><span data-stu-id="4bc64-119">When the computer is back up and running, you need to do these steps over again, starting from step three listed above (basically run Step 2 in the Deployment Wizard one more time).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

