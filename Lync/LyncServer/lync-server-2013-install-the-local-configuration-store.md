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
ms.openlocfilehash: e16d4edfb53511712c58cb41510559fcf69cfa9a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498570"
---
# <a name="install-the-local-configuration-store-in-lync-server-2013"></a><span data-ttu-id="8d4a9-102">在 Lync Server 2013 中安裝本機設定存放區</span><span class="sxs-lookup"><span data-stu-id="8d4a9-102">Install the Local Configuration store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d4a9-103">_**主題上次修改日期：** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="8d4a9-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="8d4a9-104">在遵循這些步驟之前，請確定您已使用本機系統管理員和 RTCUniversalReadOnlyAdmin 群組成員的網域使用者帳戶登入伺服器。</span><span class="sxs-lookup"><span data-stu-id="8d4a9-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmin group.</span></span>

<span data-ttu-id="8d4a9-105">若要能夠使用 Lync Server 部署嚮導執行任何動作，我們需要在伺服器上存在本機設定存放區。</span><span class="sxs-lookup"><span data-stu-id="8d4a9-105">To be able to do anything with the Lync Server Deployment Wizard, we need the Local Configuration store to exist on a server.</span></span> <span data-ttu-id="8d4a9-106">本機設定存放區是中央管理存放區的唯讀複本，它會在本機安裝 SQL Server Express 之後建立。</span><span class="sxs-lookup"><span data-stu-id="8d4a9-106">The Local Configuration store is a read-only copy of the Central Management store, which gets created after the local installation of SQL Server Express.</span></span> <span data-ttu-id="8d4a9-107">中央管理存放區本身會新增至安裝在 Standard Edition Server 或 SQL Server Express 資料庫上的現有 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="8d4a9-107">The Central Management store itself is added to the existing SQL Server database installed on the Standard Edition server or SQL Server Express-based database.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8d4a9-108">如果您之前未在此伺服器上執行 Lync Server 2013 安裝程式，系統會提示您輸入要安裝 Lync Server 2013 的磁片磁碟機和路徑。</span><span class="sxs-lookup"><span data-stu-id="8d4a9-108">If you haven’t run Lync Server 2013 setup on this server before, you’ll be prompted for a drive and path to install Lync Server 2013 to.</span></span> <span data-ttu-id="8d4a9-109">如果您的組織需要，或您有空間考慮，這會讓您安裝至系統磁片磁碟機以外的其他磁碟機。</span><span class="sxs-lookup"><span data-stu-id="8d4a9-109">This will let you install to a drive other than the system drive, if your organization requires it, or if you have space concerns.</span></span> <span data-ttu-id="8d4a9-110">您可以在 [安裝程式] 對話方塊中，將 Lync Server 檔案的安裝位置路徑變更為新的可用磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="8d4a9-110">You can just change the installation location path for the Lync Server files in the Setup dialog box to a new, available drive.</span></span> <span data-ttu-id="8d4a9-111">如果您將安裝檔案安裝至此路徑（包括 OCSCore.msi），則其他 Lync Server 2013 檔案也會部署在該路徑中。</span><span class="sxs-lookup"><span data-stu-id="8d4a9-111">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will deploy there as well.</span></span>



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a><span data-ttu-id="8d4a9-112">安裝本機設定存放區</span><span class="sxs-lookup"><span data-stu-id="8d4a9-112">To install the Local Configuration store</span></span>

1.  <span data-ttu-id="8d4a9-113">從安裝媒體，流覽至 \\ setup \\ amd64 \\Setup.exe，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8d4a9-113">From your installation media, browse to \\setup\\amd64\\Setup.exe, and then click **OK**.</span></span>

2.  <span data-ttu-id="8d4a9-114">如果系統提示您安裝 Microsoft Visual c + + 2012 可轉散發元件，請按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="8d4a9-114">If you’re prompted to install the Microsoft Visual C++ 2012 Redistributable, click **Yes**.</span></span>

3.  <span data-ttu-id="8d4a9-115">在 [ **Lync Server 2013 安裝位置** ] 頁面上，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8d4a9-115">On the **Lync Server 2013 Installation Location** page, click **OK**.</span></span>

4.  <span data-ttu-id="8d4a9-116">在 [ **使用者授權合約** ] 頁面上，查看授權條款，您必須選取 [ **我接受授權合約中的條款**]，然後按一下 **[確定]** 以繼續。</span><span class="sxs-lookup"><span data-stu-id="8d4a9-116">On the **End User License Agreement** page, review the license terms, you’ll need to select **I accept the terms in the license agreement**, and then click **OK** to be able to continue.</span></span>

5.  <span data-ttu-id="8d4a9-117">在 [部署嚮導] 頁面上，按一下 [ **安裝或更新 Lync Server 系統**]。</span><span class="sxs-lookup"><span data-stu-id="8d4a9-117">On the Deployment Wizard page, click **Install or Update Lync Server System**.</span></span>

6.  <span data-ttu-id="8d4a9-118">在 [ **Lync Server 2013** ] 頁面上，按一下 [ **步驟1：安裝本機設定存放區**] 旁邊的 [ **執行**]。</span><span class="sxs-lookup"><span data-stu-id="8d4a9-118">On the **Lync Server 2013** page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

7.  <span data-ttu-id="8d4a9-119">在 [ **安裝本機設定存放區** ] 頁面上，確定已選取 [ **直接從中央管理存放區取得** ] 選項，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8d4a9-119">On the **Install Local Configuration Store** page, make sure that the **Retrieve directly from the Central Management store** option is selected, and then click **Next**.</span></span>

8.  <span data-ttu-id="8d4a9-120">當本機伺服器設定安裝完成時，您應該按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="8d4a9-120">When the local server configuration installation is complete, you should click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

