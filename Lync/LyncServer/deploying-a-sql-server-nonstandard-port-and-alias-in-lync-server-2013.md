---
title: 在 Lync Server 2013 中部署 SQL Server 非標準埠和別名
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8721cc82651710ab5fc8158eeb6f297f80847c33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502910"
---
# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="6b2b4-102">在 Lync Server 2013 中部署 SQL Server 非標準埠和別名</span><span class="sxs-lookup"><span data-stu-id="6b2b4-102">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b2b4-103">_**主題上次修改日期：** 2015-09-16_</span><span class="sxs-lookup"><span data-stu-id="6b2b4-103">_**Topic Last Modified:** 2015-09-16_</span></span>

<span data-ttu-id="6b2b4-104">Microsoft Lync Server 2013 支援在 SQL Server 中使用非標準埠和別名。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-104">Microsoft Lync Server 2013 supports using a non-standard port and alias in SQL Server.</span></span> <span data-ttu-id="6b2b4-105">使用 SQL Server 非標準埠和別名可提高安全性，並為 Lync 部署建立更靈活的環境。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-105">Using a SQL Server non-standard port and an alias increases security and creates a more flexible environment for the Lync deployment.</span></span> <span data-ttu-id="6b2b4-106">這些步驟只是正確保護您的 Lync Server 2013 環境的單一步驟。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-106">These steps are only a single step in properly securing your Lync Server 2013 environment.</span></span> <span data-ttu-id="6b2b4-107">您應採取額外的步驟來減少 Lync Server 2013 實施的攻擊面。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-107">Additional steps should be taken to reduce the attack surface of a Lync Server 2013 implementation.</span></span>

<span data-ttu-id="6b2b4-108">下列文章說明在 Lync Server 2013 中安裝 SQL Server 非標準埠和別名所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-108">The following article describes the steps required to setup a SQL Server non-standard port and alias in Lync Server 2013.</span></span>

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="6b2b4-109">在 Lync Server 2013 中部署 SQL Server 非標準埠和別名</span><span class="sxs-lookup"><span data-stu-id="6b2b4-109">Deploying a SQL Server Non-Standard Port and Alias in Lync Server 2013</span></span>

<span data-ttu-id="6b2b4-110">Lync Server 2013 拓撲產生器支援使用 SQL Server 別名做為完整功能變數名稱 (FQDN) ，而不是在設定 Lync Server 2013 時使用實際的 SQL Server FQDN。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-110">Lync Server 2013 Topology Builder supports using a SQL Server alias as the Fully Qualified Domain Name (FQDN) instead of the actual SQL Server FQDN when configuring Lync Server 2013.</span></span> <span data-ttu-id="6b2b4-111">這可讓實際的 SQL Server FQDN 對任何惡意攻擊者隱藏。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-111">This allows the actual SQL Server FQDN to be hidden from any malicious attacker.</span></span> <span data-ttu-id="6b2b4-112">此外，使用非標準埠掩蓋實際埠，攻擊者可能會嘗試攻擊標準埠1433上的資料庫，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-112">In addition, using a non-standard port obscures the actual port from any would be attacker attempting to attack the database on the standard port 1433, as shown in the following figure.</span></span>

<span data-ttu-id="6b2b4-113">![駭客不知道要攻擊的埠號碼。](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "駭客不知道要攻擊的埠號碼。")</span><span class="sxs-lookup"><span data-stu-id="6b2b4-113">![A hacker doesn't know the port number to attack.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "A hacker doesn't know the port number to attack.")</span></span>

<span data-ttu-id="6b2b4-114">為了成功判斷使用的埠 Lync Server 2013 與 SQL Server 通訊，攻擊者必須掃描所有的埠，以取得埠資訊。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-114">In order to be successful in determining the port Lync Server 2013 is using to communicate with SQL Server, the attacker would need to scan all ports to obtain the port information.</span></span> <span data-ttu-id="6b2b4-115">攻擊者所進行的埠掃描可提高安全性偵測和停止指示的機會。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-115">A port scan by an attacker increases the chances that security can detect and stop the instruction.</span></span> <span data-ttu-id="6b2b4-116">除了使用非標準埠新增加強的安全性之外，您也可以使用 SQL Server 別名，為部署提供彈性。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-116">In addition to adding increased security with a non-standard port, you can also use a SQL Server alias to provide flexibility for the deployment.</span></span> <span data-ttu-id="6b2b4-117">在需要 SQL Server 名稱變更的情況下，這是很有用的，以便減少設定的變更。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-117">This is valuable in order to reduce configuration changes in situations where a SQL Server name change is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6b2b4-118">SQL Server 提供兩種容錯方法 (容錯移轉叢集及鏡像) 。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-118">SQL Server provides two fault tolerance methods (Failover Clustering and Mirroring).</span></span> <span data-ttu-id="6b2b4-119">使用 SQL Server 非標準埠和具有 Lync Server 2013 的別名，都支援這兩種 SQL Server 容錯方法。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-119">Both SQL Server fault tolerance methods are supported using a SQL Server non-standard port and alias with Lync Server 2013.</span></span> <span data-ttu-id="6b2b4-120">如果集區使用的 SQL Server 後端是在鏡像設定中，則當資料庫容錯移轉至鏡像的 SQL Server 時，應執行 SQL Server 後端伺服器上的 SQL browser 服務，以連線至鏡像資料庫。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-120">If the SQL Server backend used by the pool is in a mirrored configuration, then the SQL browser service on the SQL Server backend servers should be running for Front End servers to connect to the mirrored database when the databases are failed over to the mirrored SQL Server.</span></span>



</div>

<span data-ttu-id="6b2b4-121">從拓撲產生器內設定 SQL Server 資料庫連線時，或在使用 Install-CsDatabase Cmdlet 時，無法明確定義 SQL Server 非標準埠號碼，並將它與 SQL 實例產生關聯。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-121">When configuring SQL Server database connectivity from within Topology Builder, or when using the Install-CsDatabase cmdlet, it’s not possible to explicitly define a SQL Server non-standard port number and associate it with a SQL instance.</span></span> <span data-ttu-id="6b2b4-122">若要設定非標準埠，您必須使用 SQL Server 及 Windows Server 公用程式。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-122">To set a non-standard port, you’ll need to use SQL Server and Windows Server utilities.</span></span>

<span data-ttu-id="6b2b4-123">若要設定 SQL Server 非標準埠和別名以用於 Lync Server 2013，您將需要完成三個主要步驟。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-123">To set up a SQL Server non-standard port and alias for use with Lync Server 2013, you will need to complete three primary steps.</span></span> <span data-ttu-id="6b2b4-124">這些步驟包括：</span><span class="sxs-lookup"><span data-stu-id="6b2b4-124">These steps are:</span></span>

  - <span data-ttu-id="6b2b4-125">確認 Lync Server 2013 已套用最新的更新。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-125">Confirm that Lync Server 2013 has the Latest Updates Applied.</span></span>

  - <span data-ttu-id="6b2b4-126">設定 SQL Server 非標準埠和別名。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-126">Setup the SQL Server Non-Standard Port and Alias.</span></span>

  - <span data-ttu-id="6b2b4-127">使用拓撲產生器，設定使用 SQL Server 別名的 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-127">Configure Lync Server 2013 with the SQL Server alias using Topology Builder.</span></span>

  - <span data-ttu-id="6b2b4-128">發行拓撲，並驗證資料庫。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-128">Publish the Topology, and Verify the Database.</span></span>

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a><span data-ttu-id="6b2b4-129">確認 Lync Server 2013 已套用最新的更新</span><span class="sxs-lookup"><span data-stu-id="6b2b4-129">Confirm that Lync Server 2013 has the Latest Updates Applied</span></span>

<span data-ttu-id="6b2b4-130">務必將 Lync Server 2013 保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-130">It is important to keep Lync Server 2013 up to date.</span></span> <span data-ttu-id="6b2b4-131">若要檢查最近的更新及如何套用的資訊，請參閱 [Lync Server 2013 的更新](https://support.microsoft.com/kb/2809243)。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-131">To check for the most recent updates and information on how to apply them, see [Updates for Lync Server 2013](https://support.microsoft.com/kb/2809243).</span></span>

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a><span data-ttu-id="6b2b4-132">設定 SQL Server 非標準埠和別名</span><span class="sxs-lookup"><span data-stu-id="6b2b4-132">Setup the SQL Server Non-Standard Port and Alias</span></span>

<span data-ttu-id="6b2b4-133">在資料庫實例上，必須先設定 SQL Server 非標準埠和別名，才能從 Lync Server 2013 拓撲產生器參照它。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-133">The SQL Server non-standard port and alias must be set up on the database instance before it can be referenced from Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="6b2b4-134">若要設定 SQL Server 非標準埠和別名，您必須完成三個主要步驟。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-134">To set up a SQL Server non-standard port and alias, you will have to complete three primary steps.</span></span> <span data-ttu-id="6b2b4-135">這些步驟如下：</span><span class="sxs-lookup"><span data-stu-id="6b2b4-135">These steps are as follows:</span></span>

  - <span data-ttu-id="6b2b4-136">變更預設的通訊協定值 TCP/IP。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-136">Change the Default TCP/IP Protocol Values.</span></span>

  - <span data-ttu-id="6b2b4-137">建立及設定 SQL Server 別名。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-137">Create and Configure a SQL Server Alias.</span></span>

  - <span data-ttu-id="6b2b4-138">建立網域名稱系統 (DNS) 正常化名稱 (CNAME) 資源記錄。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-138">Create a Domain Name System (DNS) Canonical Name (CNAME) Resource Record.</span></span>

<span data-ttu-id="6b2b4-139">**修改預設 TCP/IP 通訊協定值**</span><span class="sxs-lookup"><span data-stu-id="6b2b4-139">**Modify the Default TCP/IP Protocol Values**</span></span>

1.  <span data-ttu-id="6b2b4-140">選取 [ **開始**]，然後選擇 [ **SQL Server Configuration Manager**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-140">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6b2b4-141">![SQL Server Management Studio 圖示](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio 圖示")</span><span class="sxs-lookup"><span data-stu-id="6b2b4-141">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="6b2b4-142">在功能窗格中，選擇展開**Sql server 實例**，選擇展開 [ **sql server 網路**設定]，然後\*\* \<instance name\> 選擇 [通訊協定\*\*]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-142">In the navigation pane, choose to expand the **SQL Server instance**, choose to expand **SQL Server Network Configuration**, and choose **Protocols for \<instance name\>**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6b2b4-143">![流覽至 TCP/IP 屬性](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "流覽至 TCP/IP 屬性")</span><span class="sxs-lookup"><span data-stu-id="6b2b4-143">![Navigate to TCP/IP Properties](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navigate to TCP/IP Properties")</span></span>

3.  <span data-ttu-id="6b2b4-144">在右窗格中，以滑鼠右鍵按一下 [ **TCP/IP**]，然後選取 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-144">In the right pane, right-click **TCP/IP**, and select **Properties**.</span></span> <span data-ttu-id="6b2b4-145">隨即會顯示 [TCP/IP 屬性] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-145">The TCP/IP Properties dialog box is displayed.</span></span>

4.  <span data-ttu-id="6b2b4-146">選取 [ **IP 位址** ] 索引標籤。[IP 位址] 索引標籤會顯示伺服器上所有使用中的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-146">Select the **IP Addresses** tab. The IP Addresses tab shows all of the active IP addresses on the server.</span></span> <span data-ttu-id="6b2b4-147">其格式為 IP1，IP2，最多 IPAll，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-147">These are in the format IP1, IP2, up to IPAll, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6b2b4-148">![開啟 TCP/IP 屬性。](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "開啟 TCP/IP 屬性。")</span><span class="sxs-lookup"><span data-stu-id="6b2b4-148">![Open TCP/IP properties.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Open TCP/IP properties.")</span></span>

5.  <span data-ttu-id="6b2b4-149">清除所有 IP 位址的 [ **TCP 動態埠** ] 欄位。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-149">Clear the **TCP Dynamic Ports** field for all IP addresses.</span></span> <span data-ttu-id="6b2b4-150">如果欄位包含零字元，則表示 SQL Server 正在接聽動態埠。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-150">If the field contains a zero character, then it means SQL Server is listening on dynamic ports.</span></span> <span data-ttu-id="6b2b4-151">請確定這些欄位已清除，而且不含零。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-151">Make sure these fields are cleared and do not contain a zero.</span></span>

6.  <span data-ttu-id="6b2b4-152">如需 Lync Server 用來連線至資料庫的 IP 位址，請確定 **Enabled** 已設定為 **[是]**，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-152">For the IP address that Lync Server will be using to connect to the database, make sure that **Enabled** is set to **Yes**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6b2b4-153">![針對正確的 IP，將啟用設為 [是]。](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "針對正確的 IP，將啟用設為 [是]。")</span><span class="sxs-lookup"><span data-stu-id="6b2b4-153">![Set enabled as Yes for the correct IP.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Set enabled as Yes for the correct IP.")</span></span>

7.  <span data-ttu-id="6b2b4-154">在對話方塊底部的 [ **IPAll** ] 區段中，于 [ **TCP 埠** ] 欄位中輸入所需的埠，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-154">In the **IPAll** section at the bottom of the dialog, enter the desired port in the **TCP Port** field, as shown in the following figure.</span></span> <span data-ttu-id="6b2b4-155">在此範例中，我們使用埠50062，但您可以使用49152和65535之間的任何埠。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-155">In this example, we use port 50062, but you can use any port between 49152 and 65535.</span></span> <span data-ttu-id="6b2b4-156">這些是指派給動態及私人使用的埠，這可確保您不會與 Lync Server 2013 部署中使用的其他通訊埠產生衝突。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-156">These are the ports assigned to dynamic and private use, and this ensures you won’t conflict with other ports being used in the Lync Server 2013 deployment.</span></span>
    
    <span data-ttu-id="6b2b4-157">![在 IPAll 區段中設定埠。](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "在 IPAll 區段中設定埠。")</span><span class="sxs-lookup"><span data-stu-id="6b2b4-157">![Set port in IPAll section.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Set port in IPAll section.")</span></span>

8.  <span data-ttu-id="6b2b4-158">選擇 **[確定** ]，結束 [TCP/IP 屬性] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-158">Choose **OK** to exit the TCP/IP Properties dialog.</span></span>

9.  <span data-ttu-id="6b2b4-159">在 SQL Server Configuration Manager 的左窗格中，選取 [ **Sql Server 服務** ]，以重新開機 sql server 實例。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-159">Restart the SQL Server instance by selecting **SQL Server Services** in the left pane of SQL Server Configuration Manager.</span></span> <span data-ttu-id="6b2b4-160">然後在右窗格中以滑鼠右鍵按一下 **[SQL Server \<instance name\> \*\* ]，然後選取 [**重新開機\*\*]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-160">Then right-click **SQL Server \<instance name\>** in the right pane, and select **Restart**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6b2b4-161">![針對 instance 重設 SQL Server 服務。](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "針對 instance 重設 SQL Server 服務。")</span><span class="sxs-lookup"><span data-stu-id="6b2b4-161">![Reset the SQL Server service for instance.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Reset the SQL Server service for instance.")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6b2b4-162">請確定您更新防火牆設定，以容納新的 SQL Server 埠。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-162">Make sure you update your firewall settings to accommodate the new SQL Server port.</span></span>



</div>

<span data-ttu-id="6b2b4-163">**建立及設定 SQL Server 別名**</span><span class="sxs-lookup"><span data-stu-id="6b2b4-163">**Create and Configure a SQL Server Alias**</span></span>

1.  <span data-ttu-id="6b2b4-164">選取 [ **開始**]，然後選擇 [ **SQL Server Configuration Manager**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-164">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6b2b4-165">![SQL Server Management Studio 圖示](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio 圖示")</span><span class="sxs-lookup"><span data-stu-id="6b2b4-165">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="6b2b4-166">在左窗格中，選擇展開 **[Sql Server 實例**]，選擇展開 **[sql Native Client \<version\> Configuration**]，然後選擇 [ **別名**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-166">In the left pane, choose to expand **SQL Server instance**, choose to expand **SQL Native Client \<version\> Configuration**, and then choose **Aliases**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6b2b4-167">![SQL Server Configuration Manager 中的別名。](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "SQL Server Configuration Manager 中的別名。")</span><span class="sxs-lookup"><span data-stu-id="6b2b4-167">![Aliases in SQL Server Configuration Manager.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliases in SQL Server Configuration Manager.")</span></span>

3.  <span data-ttu-id="6b2b4-168">以滑鼠右鍵按一下 [ **別名**]，然後選取 [ **新增別名 ...**]。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-168">Right-click **Aliases**, and select **New Alias…**.</span></span>

4.  <span data-ttu-id="6b2b4-169">輸入 **別名名稱**、 **埠號碼**、 **通訊協定**和 **伺服器**，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-169">Enter the **Alias Name**, **Port Number**, **Protocol**, and **Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6b2b4-170">![建立新的別名](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "建立新的別名")</span><span class="sxs-lookup"><span data-stu-id="6b2b4-170">![Creating a new alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Creating a new alias")</span></span>
    
    <div>
    

    > [!CAUTION]  
    > <span data-ttu-id="6b2b4-171">請務必輸入您在上一個步驟中使用的相同非標準埠，因為這是 SQL Server 將要接聽的埠。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-171">Make sure to enter the same non-standard port you used in the previous step since that is the port SQL Server will be listening on.</span></span> <span data-ttu-id="6b2b4-172">如果已設定的別名連接至錯誤的 SQL Server FQDN 或實例，請停用，然後重新啟用相關聯的網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-172">If a configured alias is connecting to the wrong SQL Server FQDN or Instance, disable and then re-enable the associated network protocol.</span></span> <span data-ttu-id="6b2b4-173">這樣做會清除任何快取的連線資訊，並允許用戶端正確連接。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-173">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>

    
    </div>

<span data-ttu-id="6b2b4-174">**建立 DNS CNAME 資源記錄**</span><span class="sxs-lookup"><span data-stu-id="6b2b4-174">**Create a DNS CNAME Resource Record**</span></span>

1.  <span data-ttu-id="6b2b4-175">登入管理 DNS 的電腦。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-175">Sign into the computer managing DNS.</span></span>

2.  <span data-ttu-id="6b2b4-176">選取 [ **啟動**]，然後選擇 [ **伺服器管理員**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-176">Select **Start**, and choose **Server Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6b2b4-177">![開啟伺服器管理員](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "開啟伺服器管理員")</span><span class="sxs-lookup"><span data-stu-id="6b2b4-177">![Opening Server Manager](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Opening Server Manager")</span></span>

3.  <span data-ttu-id="6b2b4-178">選擇 [ **工具** ] 下拉式清單，然後選取 [ **DNS**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-178">Choose the **Tools** drop-down, and select **DNS**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6b2b4-179">![從 [伺服器管理員] 開啟 DNS。](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "從 [伺服器管理員] 開啟 DNS。")</span><span class="sxs-lookup"><span data-stu-id="6b2b4-179">![Opening DNS from Server Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Opening DNS from Server Manager.")</span></span>

4.  <span data-ttu-id="6b2b4-180">在左窗格中，展開 [伺服器名稱] 節點，展開 [正向對應區域] 節點，然後選擇相關的網域。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-180">In the left pane, expand the server name node, expand the Forward Lookup Zones node, and choose the relevant domain.</span></span>

5.  <span data-ttu-id="6b2b4-181">在網域上按一下滑鼠右鍵，然後選取 [ **新增別名 (CNAME) ...**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-181">Right-click the domain, and select **New Alias (CNAME)…**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6b2b4-182">![選取選項以建立新的別名 CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "選取選項以建立新的別名 CNAME")</span><span class="sxs-lookup"><span data-stu-id="6b2b4-182">![Selecting option to create a new alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selecting option to create a new alias CNAME")</span></span>

6.  <span data-ttu-id="6b2b4-183">輸入 **別名名稱** 和 **SQL Server 的 FQDN**，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-183">Enter the **Alias Name** and the **FQDN for SQL Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6b2b4-184">![填入 [新增別名 CNAME] 對話方塊。](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "填入 [新增別名 CNAME] 對話方塊。")</span><span class="sxs-lookup"><span data-stu-id="6b2b4-184">![Filling in the new alias CNAME dialog.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Filling in the new alias CNAME dialog.")</span></span>

7.  <span data-ttu-id="6b2b4-185">選擇 **[確定]** 以儲存 CNAME 並在 DNS 管理員中查看。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-185">Choose **OK** to save the CNAME and view it in DNS Manager.</span></span>

</div>

<div>

## <a name="validate-database-connectivity"></a><span data-ttu-id="6b2b4-186">驗證資料庫連線能力</span><span class="sxs-lookup"><span data-stu-id="6b2b4-186">Validate Database Connectivity</span></span>

<span data-ttu-id="6b2b4-187">有許多不同的方式可確保其正常運作。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-187">There are many different ways to make sure it is working.</span></span> <span data-ttu-id="6b2b4-188">您想確定 SQL Server 資料庫正在使用別名在指定的埠上接聽。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-188">You want to make sure that the SQL Server database is listening on the specified port using the alias.</span></span> <span data-ttu-id="6b2b4-189">您可以使用 **netstat** 和 **telnet** 命令來完成快速檢查。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-189">A quick check can be completed using the **netstat** and **telnet** commands.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6b2b4-190">「Telnet 用戶端」是 Windows Server 附帶但必須安裝的功能。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-190">Telnet Client is a Feature that comes with Windows Server but that must be installed.</span></span> <span data-ttu-id="6b2b4-191">您可以從 [管理] 功能表中，開啟 [伺服器管理員] 並選取 [新增角色及功能]，即可安裝 Windows Server 功能。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-191">A Windows Server Feature can be installed by opening Server Manager and selecting Add Roles and Features from the Manage menu.</span></span>



</div>

<span data-ttu-id="6b2b4-192">**使用 netstat 和 telnet 驗證資料庫連線能力**</span><span class="sxs-lookup"><span data-stu-id="6b2b4-192">**Use netstat and telnet to verify database connectivity**</span></span>

1.  <span data-ttu-id="6b2b4-193">選取 [ **開始**]，然後輸入 **cmd** 以開啟命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-193">Select **Start**, and type **cmd** to open a command prompt.</span></span>

2.  <span data-ttu-id="6b2b4-194">輸入 **netstat-a-f**，並確認 SQL Server 正在使用正確的埠執行，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-194">Type **netstat -a -f**, and confirm that SQL Server is running with the correct port, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6b2b4-195">![使用 netstat 驗證埠。](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "使用 netstat 驗證埠。")</span><span class="sxs-lookup"><span data-stu-id="6b2b4-195">![Using netstat to verify port.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Using netstat to verify port.")</span></span>

3.  <span data-ttu-id="6b2b4-196">輸入\*\*telnet \<alias name\> \<port \#\> \*\* ，以確認 SQL Server 實例的連線。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-196">Type **telnet \<alias name\> \<port \#\>** to confirm the connection to the SQL Server instance.</span></span> <span data-ttu-id="6b2b4-197">如果連線成功，telnet 將會連線，而且您不會看到錯誤。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-197">If the connection is successful, telnet will connect and you shouldn’t see an error.</span></span> <span data-ttu-id="6b2b4-198">這會顯示 SQL Server 實例正在使用正確的別名在正確的埠上接聽。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-198">This shows that the SQL Server instance is listening on the correct port with the correct alias.</span></span> <span data-ttu-id="6b2b4-199">如果連線到 SQL Server 資料庫時發生問題，telnet 會顯示無法進行連線的錯誤。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-199">If there’s a problem connecting to the SQL Server database, then telnet shows an error that the connection cannot be made.</span></span> <span data-ttu-id="6b2b4-200">現在，您已在資料庫伺服器上檢查資料庫連線能力，您可以透過網路上的 Lync Server (執行相同的作業) 並確定沒有任何防火牆封鎖存取方式。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-200">Now that you have checked database connectivity on the database server, you can do the same thing from Lync Server (over the network) and make sure there aren’t any firewalls blocking access along the way.</span></span>

</div>

<div>

## <a name="conclusion"></a><span data-ttu-id="6b2b4-201">總結</span><span class="sxs-lookup"><span data-stu-id="6b2b4-201">Conclusion</span></span>

<span data-ttu-id="6b2b4-202">在設定 SQL Server 別名之後，您可以在拓撲產生器工具中使用它來建立 Lync Server 2013 拓撲。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-202">Once the SQL Server alias has been configured, you can use it to create a Lync Server 2013 topology in the Topology Builder tool.</span></span> <span data-ttu-id="6b2b4-203">如需拓撲的詳細資訊，請參閱 [在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="6b2b4-203">For more information about topologies, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6b2b4-204">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6b2b4-204">See Also</span></span>


<span data-ttu-id="6b2b4-205">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md)  
[Lync Server 2013 中的安全性規劃](lync-server-2013-planning-for-security.md)</span><span class="sxs-lookup"><span data-stu-id="6b2b4-205">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[Planning for security in Lync Server 2013](lync-server-2013-planning-for-security.md)</span></span>  
[<span data-ttu-id="6b2b4-206">在 Lync Server 2013 中定義及設定拓撲</span><span class="sxs-lookup"><span data-stu-id="6b2b4-206">Defining and configuring the topology in Lync Server 2013</span></span>](lync-server-2013-defining-and-configuring-the-topology.md)  
[<span data-ttu-id="6b2b4-207">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b2b4-207">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

