---
title: Lync Server 2013： 安裝本機設定存放區
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
ms.openlocfilehash: 478f45ff682b399f911b41d11a16c802181d14ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a><span data-ttu-id="03648-102">在 Lync Server 2013 中安裝本機設定存放區</span><span class="sxs-lookup"><span data-stu-id="03648-102">Install the Local Configuration store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03648-103">_**上次修改主題：** 2014 年 06 月 27 日_</span><span class="sxs-lookup"><span data-stu-id="03648-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="03648-104">執行下列步驟之前，請確定您登入使用網域使用者帳戶是本機系統管理員和擁有 RTCUniversalReadOnlyAdmin 群組成員的伺服器。</span><span class="sxs-lookup"><span data-stu-id="03648-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmin group.</span></span>

<span data-ttu-id="03648-105">若要能夠做任何處理 Lync Server 部署精靈，我們需要存在於伺服器上的本機設定存放區。</span><span class="sxs-lookup"><span data-stu-id="03648-105">To be able to do anything with the Lync Server Deployment Wizard, we need the Local Configuration store to exist on a server.</span></span> <span data-ttu-id="03648-106">本機設定存放區是中央管理存放區，這會取得建立 SQL Server Express 的本機安裝後的唯讀複本。</span><span class="sxs-lookup"><span data-stu-id="03648-106">The Local Configuration store is a read-only copy of the Central Management store, which gets created after the local installation of SQL Server Express.</span></span> <span data-ttu-id="03648-107">安裝 Standard Edition server 或 SQL Server Express 式資料庫上的現有 SQL Server 資料庫會加入中央管理存放區本身擷取。</span><span class="sxs-lookup"><span data-stu-id="03648-107">The Central Management store itself is added to the existing SQL Server database installed on the Standard Edition server or SQL Server Express-based database.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="03648-108">如果您還沒有執行 Lync Server 2013 安裝程式之前這部伺服器上，系統會提示您的路徑和機安裝 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="03648-108">If you haven’t run Lync Server 2013 setup on this server before, you’ll be prompted for a drive and path to install Lync Server 2013 to.</span></span> <span data-ttu-id="03648-109">這可讓您安裝磁碟機以外的系統磁碟機中，如果貴組織需要它，或者如果您有空間考量。</span><span class="sxs-lookup"><span data-stu-id="03648-109">This will let you install to a drive other than the system drive, if your organization requires it, or if you have space concerns.</span></span> <span data-ttu-id="03648-110">您只可以變更設定] 對話方塊中的 Lync Server 檔案的安裝位置路徑至新的可用的磁碟機。</span><span class="sxs-lookup"><span data-stu-id="03648-110">You can just change the installation location path for the Lync Server files in the Setup dialog box to a new, available drive.</span></span> <span data-ttu-id="03648-111">如果您將安裝檔案安裝到此路徑，包括 OCSCore.msi，Lync Server 2013 檔案的其餘部分將會部署那里也。</span><span class="sxs-lookup"><span data-stu-id="03648-111">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will deploy there as well.</span></span>



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a><span data-ttu-id="03648-112">若要安裝本機設定存放區</span><span class="sxs-lookup"><span data-stu-id="03648-112">To install the Local Configuration store</span></span>

1.  <span data-ttu-id="03648-113">從安裝媒體，瀏覽至\\安裝\\amd64\\Setup.exe，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="03648-113">From your installation media, browse to \\setup\\amd64\\Setup.exe, and then click **OK**.</span></span>

2.  <span data-ttu-id="03648-114">如果系統提示您安裝 Microsoft Visual c + + 2012年可轉散發套件，按一下 [**是**]。</span><span class="sxs-lookup"><span data-stu-id="03648-114">If you’re prompted to install the Microsoft Visual C++ 2012 Redistributable, click **Yes**.</span></span>

3.  <span data-ttu-id="03648-115">在**Lync Server 2013 的安裝位置**] 頁面上，按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="03648-115">On the **Lync Server 2013 Installation Location** page, click **OK**.</span></span>

4.  <span data-ttu-id="03648-116">在 [**使用者授權合約**] 頁面上，檢閱授權合約，您需要以選取 [**我接受授權合約中的條款**]，然後按一下 **[確定]** 若要能夠繼續。</span><span class="sxs-lookup"><span data-stu-id="03648-116">On the **End User License Agreement** page, review the license terms, you’ll need to select **I accept the terms in the license agreement**, and then click **OK** to be able to continue.</span></span>

5.  <span data-ttu-id="03648-117">在 [部署精靈] 頁面上，按一下 [**安裝或更新 Lync Server 系統**]。</span><span class="sxs-lookup"><span data-stu-id="03648-117">On the Deployment Wizard page, click **Install or Update Lync Server System**.</span></span>

6.  <span data-ttu-id="03648-118">在**Lync Server 2013** ] 頁面中下, 一步] 為**步驟 1： 安裝本機設定存放區**，按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="03648-118">On the **Lync Server 2013** page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

7.  <span data-ttu-id="03648-119">在**安裝本機設定存放區**] 頁面上，請確定已選取 [**直接從中央管理存放區擷取**] 選項，然後再按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="03648-119">On the **Install Local Configuration Store** page, make sure that the **Retrieve directly from the Central Management store** option is selected, and then click **Next**.</span></span>

8.  <span data-ttu-id="03648-120">本機伺服器設定安裝完成時，您應該按一下 [**完成]**。</span><span class="sxs-lookup"><span data-stu-id="03648-120">When the local server configuration installation is complete, you should click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

