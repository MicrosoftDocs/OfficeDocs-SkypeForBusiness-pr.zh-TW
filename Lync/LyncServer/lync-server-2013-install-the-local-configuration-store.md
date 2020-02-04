---
title: Lync Server 2013：安裝本機設定存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4af6d4b6dfe203f69a6b104b6ade636d2658178
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a><span data-ttu-id="6f846-102">在 Lync Server 2013 中安裝本機設定存放區</span><span class="sxs-lookup"><span data-stu-id="6f846-102">Install the Local Configuration store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f846-103">_**主題上次修改日期：** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="6f846-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="6f846-104">在執行下列步驟之前，請確認您已使用網域使用者帳戶登入伺服器，且這兩者都是本機管理員，且是 RTCUniversalReadOnlyAdmin 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="6f846-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmin group.</span></span>

<span data-ttu-id="6f846-105">若要能夠使用 Lync Server 部署嚮導執行任何動作，我們必須在伺服器上存在本機配置存放區。</span><span class="sxs-lookup"><span data-stu-id="6f846-105">To be able to do anything with the Lync Server Deployment Wizard, we need the Local Configuration store to exist on a server.</span></span> <span data-ttu-id="6f846-106">本機配置存放區是集中式管理儲存體的唯讀複本，在本機安裝 SQL Server Express 之後就會建立。</span><span class="sxs-lookup"><span data-stu-id="6f846-106">The Local Configuration store is a read-only copy of the Central Management store, which gets created after the local installation of SQL Server Express.</span></span> <span data-ttu-id="6f846-107">中央管理商店本身會新增至安裝在標準版 server 或 SQL Server Express 資料庫上的現有 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="6f846-107">The Central Management store itself is added to the existing SQL Server database installed on the Standard Edition server or SQL Server Express-based database.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6f846-108">如果您之前沒有在此伺服器上執行 Lync Server 2013 設定，系統會提示您輸入安裝 Lync Server 2013 的磁片磁碟機和路徑。</span><span class="sxs-lookup"><span data-stu-id="6f846-108">If you haven’t run Lync Server 2013 setup on this server before, you’ll be prompted for a drive and path to install Lync Server 2013 to.</span></span> <span data-ttu-id="6f846-109">這可讓您安裝到系統磁片磁碟機以外的磁碟機（如果您的組織需要的話），或者您是否有空間擔心。</span><span class="sxs-lookup"><span data-stu-id="6f846-109">This will let you install to a drive other than the system drive, if your organization requires it, or if you have space concerns.</span></span> <span data-ttu-id="6f846-110">您只需將 [設定] 對話方塊中的 Lync Server 檔案安裝位置路徑變更為新的可用磁片磁碟機即可。</span><span class="sxs-lookup"><span data-stu-id="6f846-110">You can just change the installation location path for the Lync Server files in the Setup dialog box to a new, available drive.</span></span> <span data-ttu-id="6f846-111">如果您將安裝檔案安裝到此路徑，包括 OCSCore，則其餘的 Lync Server 2013 檔案也會部署在該處。</span><span class="sxs-lookup"><span data-stu-id="6f846-111">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will deploy there as well.</span></span>



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a><span data-ttu-id="6f846-112">安裝本機配置存放區</span><span class="sxs-lookup"><span data-stu-id="6f846-112">To install the Local Configuration store</span></span>

1.  <span data-ttu-id="6f846-113">從您的安裝媒體，流覽\\至\\[\\設定 Amd64] Setup.exe，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6f846-113">From your installation media, browse to \\setup\\amd64\\Setup.exe, and then click **OK**.</span></span>

2.  <span data-ttu-id="6f846-114">如果系統提示您安裝 Microsoft Visual c + + 2012 可轉散發元件，請按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="6f846-114">If you’re prompted to install the Microsoft Visual C++ 2012 Redistributable, click **Yes**.</span></span>

3.  <span data-ttu-id="6f846-115">在 [ **Lync Server 2013 安裝位置**] 頁面上，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6f846-115">On the **Lync Server 2013 Installation Location** page, click **OK**.</span></span>

4.  <span data-ttu-id="6f846-116">在 [**使用者授權合約**] 頁面上，查看 [授權條款]，您必須選取 **[我接受授權合約中的條款**]，然後按一下 **[確定]** 以繼續進行。</span><span class="sxs-lookup"><span data-stu-id="6f846-116">On the **End User License Agreement** page, review the license terms, you’ll need to select **I accept the terms in the license agreement**, and then click **OK** to be able to continue.</span></span>

5.  <span data-ttu-id="6f846-117">在 [部署嚮導] 頁面上，按一下 [**安裝或更新 Lync Server 系統**]。</span><span class="sxs-lookup"><span data-stu-id="6f846-117">On the Deployment Wizard page, click **Install or Update Lync Server System**.</span></span>

6.  <span data-ttu-id="6f846-118">在 [ **Lync Server 2013** ] 頁面上，按一下 [ **Step1：安裝本機配置存放區**] 旁的 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="6f846-118">On the **Lync Server 2013** page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

7.  <span data-ttu-id="6f846-119">在 [**安裝本機設定儲存區**] 頁面上，確認已選取 [**直接從中央管理儲存**] 選項進行檢索，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6f846-119">On the **Install Local Configuration Store** page, make sure that the **Retrieve directly from the Central Management store** option is selected, and then click **Next**.</span></span>

8.  <span data-ttu-id="6f846-120">本機伺服器設定安裝完成後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="6f846-120">When the local server configuration installation is complete, you should click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

