---
title: Lync Server 2013：安裝 Lync Server 伺服器元件
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
ms.openlocfilehash: 4f039f9363469663410f08f078a3b7e17a170075
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a><span data-ttu-id="efd64-102">安裝 Lync Server 2013 的伺服器元件</span><span class="sxs-lookup"><span data-stu-id="efd64-102">Install server components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efd64-103">_**主題上次修改日期：** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="efd64-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="efd64-104">在遵循這些步驟之前，請確認您已登入的網域使用者帳戶是本機管理員，且在 Active Directory 中是 RTCUniversalReadOnlyAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="efd64-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmins group in Active Directory.</span></span>

<span data-ttu-id="efd64-105">Lync Server 部署嚮導是用來安裝每個 Lync 伺服器角色所需的元件，以及啟動伺服器。</span><span class="sxs-lookup"><span data-stu-id="efd64-105">The Lync Server Deployment Wizard is used to install the needed components for each Lync server role and to activate the server.</span></span> <span data-ttu-id="efd64-106">本文將引導您逐步完成在 Lync 基礎結構中部署標準版伺服器或前端伺服器的步驟。</span><span class="sxs-lookup"><span data-stu-id="efd64-106">This article walks you through the steps of deploying a Standard Edition server or a Front End Server in your Lync infrastructure.</span></span>

<div>

## <a name="to-install-lync-server-components"></a><span data-ttu-id="efd64-107">若要安裝 Lync Server 元件</span><span class="sxs-lookup"><span data-stu-id="efd64-107">To install Lync Server components</span></span>

1.  <span data-ttu-id="efd64-108">如果未執行 Lync Server 部署嚮導，請在您要安裝 Lync 的伺服器上啟動。</span><span class="sxs-lookup"><span data-stu-id="efd64-108">If the Lync Server Deployment Wizard isn’t running, start it on the server you want to install Lync onto.</span></span>

2.  <span data-ttu-id="efd64-109">按一下 [**安裝或更新 Lync Server 系統**]。</span><span class="sxs-lookup"><span data-stu-id="efd64-109">Click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="efd64-110">在 [部署嚮導] 中，確認 [**步驟1：安裝本機設定儲存區**] 有一個綠色的核取記號，這表示此伺服器已成功安裝該商店的本機複本。</span><span class="sxs-lookup"><span data-stu-id="efd64-110">In the Deployment Wizard, confirm that **Step 1: Install Local Configuration Store** has a green check mark, which means that this server has a local copy of the store installed successfully.</span></span> <span data-ttu-id="efd64-111">如果未核取，您必須在伺服器上安裝本機配置存放區。</span><span class="sxs-lookup"><span data-stu-id="efd64-111">If it’s not checked, you need to install the Local Configuration store on the server.</span></span> <span data-ttu-id="efd64-112">請依照在[Lync Server 2013 中安裝本機設定存儲區中](lync-server-2013-install-the-local-configuration-store.md)的步驟操作，然後回到這裡。</span><span class="sxs-lookup"><span data-stu-id="efd64-112">Follow the steps at [Install the Local Configuration store in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) and then come back here.</span></span>

4.  <span data-ttu-id="efd64-113">當您準備好要在伺服器上安裝 Lync Server 2013 元件時，請按一下 [步驟2：設定] 旁的 [**執行**]，**或移除 [lync server 元件**]。</span><span class="sxs-lookup"><span data-stu-id="efd64-113">When you’re ready to install the Lync Server 2013 components on your server, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

5.  <span data-ttu-id="efd64-114">在 [**設定 Lync Server 元件**] 頁面上，按一下 **[下一步]** 以設定您在已發佈拓撲中定義的元件。</span><span class="sxs-lookup"><span data-stu-id="efd64-114">On the **Set Up Lync Server Components** page, click **Next** to set up components as defined in your published topology.</span></span>

6.  <span data-ttu-id="efd64-115">[**執行命令**] 頁面會在設定發生時顯示命令和安裝資訊摘要。</span><span class="sxs-lookup"><span data-stu-id="efd64-115">The **Executing Commands** page will display a summary of commands and installation information as the set up takes place.</span></span> <span data-ttu-id="efd64-116">完成後，您可以使用清單來選取要查看的記錄，然後按一下 [**查看記錄**]。</span><span class="sxs-lookup"><span data-stu-id="efd64-116">When it’s done, you can use the list to select a log to view, and then click **View Log**.</span></span>

7.  <span data-ttu-id="efd64-117">當 Lync Server 2013 元件設定完成，且您視需要查看記錄時，請按一下 **[完成]** ，以在安裝中完成此步驟。</span><span class="sxs-lookup"><span data-stu-id="efd64-117">When Lync Server 2013 components setup is done, and you’ve reviewed the logs as needed, click **Finish** to complete this step in the installation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="efd64-118">如果系統提示您重新開機伺服器（如果需要安裝 Windows 桌面體驗，可能會發生這種情況），請務必這麼做。</span><span class="sxs-lookup"><span data-stu-id="efd64-118">If you’re prompted to restart the server (which might happen if Windows Desktop Experience needed to be installed), definitely do that.</span></span> <span data-ttu-id="efd64-119">當電腦重新開機並繼續執行時，您需要再次執行這些步驟，從前面所列的步驟3開始（基本上在 [部署嚮導] 中再執行一次步驟2）。</span><span class="sxs-lookup"><span data-stu-id="efd64-119">When the computer is back up and running, you need to do these steps over again, starting from step three listed above (basically run Step 2 in the Deployment Wizard one more time).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

