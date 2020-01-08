---
title: 在 Lync Server 2013  中部署 SQL Server 非標準連接埠和別名
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35365cbd43aa3bea9afe5cdd036bd3834fae5037
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="3d423-102">在 Lync Server 2013  中部署 SQL Server 非標準連接埠和別名</span><span class="sxs-lookup"><span data-stu-id="3d423-102">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d423-103">_**主題上次修改日期：** 2015-09-16_</span><span class="sxs-lookup"><span data-stu-id="3d423-103">_**Topic Last Modified:** 2015-09-16_</span></span>

<span data-ttu-id="3d423-104">Microsoft Lync Server 2013 支援在 SQL Server 中使用非標準埠和別名。</span><span class="sxs-lookup"><span data-stu-id="3d423-104">Microsoft Lync Server 2013 supports using a non-standard port and alias in SQL Server.</span></span> <span data-ttu-id="3d423-105">使用 SQL Server 非標準埠和別名可提高安全性，並為 Lync 部署建立更具彈性的環境。</span><span class="sxs-lookup"><span data-stu-id="3d423-105">Using a SQL Server non-standard port and an alias increases security and creates a more flexible environment for the Lync deployment.</span></span> <span data-ttu-id="3d423-106">這些步驟僅適用于適當地保護 Lync Server 2013 環境的單一步驟。</span><span class="sxs-lookup"><span data-stu-id="3d423-106">These steps are only a single step in properly securing your Lync Server 2013 environment.</span></span> <span data-ttu-id="3d423-107">若要減少 Lync Server 2013 實現的受攻擊面，請採取其他步驟。</span><span class="sxs-lookup"><span data-stu-id="3d423-107">Additional steps should be taken to reduce the attack surface of a Lync Server 2013 implementation.</span></span>

<span data-ttu-id="3d423-108">下列文章說明在 Lync Server 2013 中設定 SQL Server 非標準埠和別名所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="3d423-108">The following article describes the steps required to setup a SQL Server non-standard port and alias in Lync Server 2013.</span></span>

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="3d423-109">在 Lync Server 2013 中部署 SQL Server 非標準埠和別名</span><span class="sxs-lookup"><span data-stu-id="3d423-109">Deploying a SQL Server Non-Standard Port and Alias in Lync Server 2013</span></span>

<span data-ttu-id="3d423-110">Lync Server 2013 拓撲建立器支援使用 SQL Server 別名作為完整功能變數名稱（FQDN），而不是在設定 Lync Server 2013 時實際的 SQL Server FQDN。</span><span class="sxs-lookup"><span data-stu-id="3d423-110">Lync Server 2013 Topology Builder supports using a SQL Server alias as the Fully Qualified Domain Name (FQDN) instead of the actual SQL Server FQDN when configuring Lync Server 2013.</span></span> <span data-ttu-id="3d423-111">這可讓任何惡意攻擊者都能隱藏實際的 SQL Server FQDN。</span><span class="sxs-lookup"><span data-stu-id="3d423-111">This allows the actual SQL Server FQDN to be hidden from any malicious attacker.</span></span> <span data-ttu-id="3d423-112">此外，使用非標準埠掩蓋實際的埠，因為攻擊者試圖在標準埠1433上攻擊資料庫，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="3d423-112">In addition, using a non-standard port obscures the actual port from any would be attacker attempting to attack the database on the standard port 1433, as shown in the following figure.</span></span>

<span data-ttu-id="3d423-113">![駭客不知道要攻擊的埠號碼。](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "駭客不知道要攻擊的埠號碼。")</span><span class="sxs-lookup"><span data-stu-id="3d423-113">![A hacker doesn't know the port number to attack.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "A hacker doesn't know the port number to attack.")</span></span>

<span data-ttu-id="3d423-114">若要成功判斷 Lync Server 2013 用來與 SQL Server 通訊的埠，攻擊者需要掃描所有埠以取得埠資訊。</span><span class="sxs-lookup"><span data-stu-id="3d423-114">In order to be successful in determining the port Lync Server 2013 is using to communicate with SQL Server, the attacker would need to scan all ports to obtain the port information.</span></span> <span data-ttu-id="3d423-115">由攻擊者進行的埠掃描可提高安全性檢測並停止指示的機會。</span><span class="sxs-lookup"><span data-stu-id="3d423-115">A port scan by an attacker increases the chances that security can detect and stop the instruction.</span></span> <span data-ttu-id="3d423-116">除了使用非標準埠增加安全性之外，您也可以使用 SQL Server 別名來提供部署的彈性。</span><span class="sxs-lookup"><span data-stu-id="3d423-116">In addition to adding increased security with a non-standard port, you can also use a SQL Server alias to provide flexibility for the deployment.</span></span> <span data-ttu-id="3d423-117">此功能可讓您在需要變更 SQL Server 名稱的情況下，減少設定變更的價值。</span><span class="sxs-lookup"><span data-stu-id="3d423-117">This is valuable in order to reduce configuration changes in situations where a SQL Server name change is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3d423-118">SQL Server 提供兩種容錯方法（容錯移轉叢集及鏡像）。</span><span class="sxs-lookup"><span data-stu-id="3d423-118">SQL Server provides two fault tolerance methods (Failover Clustering and Mirroring).</span></span> <span data-ttu-id="3d423-119">在 Lync Server 2013 使用 SQL Server 非標準埠和別名，支援這兩種 SQL Server 容錯方法。</span><span class="sxs-lookup"><span data-stu-id="3d423-119">Both SQL Server fault tolerance methods are supported using a SQL Server non-standard port and alias with Lync Server 2013.</span></span> <span data-ttu-id="3d423-120">如果該池使用的 SQL Server 後端是在鏡像設定中，則 SQL Server 後端伺服器上的 SQL 瀏覽器服務應該在資料庫發生故障時，連線到鏡像資料庫，以便連線到鏡像的 SQL伺服器.</span><span class="sxs-lookup"><span data-stu-id="3d423-120">If the SQL Server backend used by the pool is in a mirrored configuration, then the SQL browser service on the SQL Server backend servers should be running for Front End servers to connect to the mirrored database when the databases are failed over to the mirrored SQL Server.</span></span>



</div>

<span data-ttu-id="3d423-121">從拓撲建立器中設定 SQL Server 資料庫連線，或使用 CsDatabase Cmdlet 時，無法明確定義 SQL Server 非標準埠編號，並將它與 SQL 實例建立關聯。</span><span class="sxs-lookup"><span data-stu-id="3d423-121">When configuring SQL Server database connectivity from within Topology Builder, or when using the Install-CsDatabase cmdlet, it’s not possible to explicitly define a SQL Server non-standard port number and associate it with a SQL instance.</span></span> <span data-ttu-id="3d423-122">若要設定非標準埠，您必須使用 SQL Server 和 Windows Server 實用程式。</span><span class="sxs-lookup"><span data-stu-id="3d423-122">To set a non-standard port, you’ll need to use SQL Server and Windows Server utilities.</span></span>

<span data-ttu-id="3d423-123">若要設定與 Lync Server 2013 搭配使用的 SQL Server 非標準埠和別名，您必須完成三個主要步驟。</span><span class="sxs-lookup"><span data-stu-id="3d423-123">To set up a SQL Server non-standard port and alias for use with Lync Server 2013, you will need to complete three primary steps.</span></span> <span data-ttu-id="3d423-124">這些步驟如下：</span><span class="sxs-lookup"><span data-stu-id="3d423-124">These steps are:</span></span>

  - <span data-ttu-id="3d423-125">確認 Lync Server 2013 已套用最新的更新。</span><span class="sxs-lookup"><span data-stu-id="3d423-125">Confirm that Lync Server 2013 has the Latest Updates Applied.</span></span>

  - <span data-ttu-id="3d423-126">設定 SQL Server 非標準埠和別名。</span><span class="sxs-lookup"><span data-stu-id="3d423-126">Setup the SQL Server Non-Standard Port and Alias.</span></span>

  - <span data-ttu-id="3d423-127">使用 [拓撲建立器] 來設定 Lync Server 2013 與 SQL Server 別名。</span><span class="sxs-lookup"><span data-stu-id="3d423-127">Configure Lync Server 2013 with the SQL Server alias using Topology Builder.</span></span>

  - <span data-ttu-id="3d423-128">發佈拓撲結構，並驗證資料庫。</span><span class="sxs-lookup"><span data-stu-id="3d423-128">Publish the Topology, and Verify the Database.</span></span>

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a><span data-ttu-id="3d423-129">確認 Lync Server 2013 已套用最新的更新</span><span class="sxs-lookup"><span data-stu-id="3d423-129">Confirm that Lync Server 2013 has the Latest Updates Applied</span></span>

<span data-ttu-id="3d423-130">請務必將 Lync Server 2013 保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="3d423-130">It is important to keep Lync Server 2013 up to date.</span></span> <span data-ttu-id="3d423-131">若要查看最新的更新及如何套用的相關資訊，請參閱[Lync Server 2013 更新](http://support.microsoft.com/kb/2809243)。</span><span class="sxs-lookup"><span data-stu-id="3d423-131">To check for the most recent updates and information on how to apply them, see [Updates for Lync Server 2013](http://support.microsoft.com/kb/2809243).</span></span>

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a><span data-ttu-id="3d423-132">設定 SQL Server 非標準埠和別名</span><span class="sxs-lookup"><span data-stu-id="3d423-132">Setup the SQL Server Non-Standard Port and Alias</span></span>

<span data-ttu-id="3d423-133">您必須先在資料庫實例上設定 SQL Server 非標準埠和別名，才能從 Lync Server 2013 拓撲產生器引用它。</span><span class="sxs-lookup"><span data-stu-id="3d423-133">The SQL Server non-standard port and alias must be set up on the database instance before it can be referenced from Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="3d423-134">若要設定 SQL Server 非標準埠和別名，您必須完成三個主要步驟。</span><span class="sxs-lookup"><span data-stu-id="3d423-134">To set up a SQL Server non-standard port and alias, you will have to complete three primary steps.</span></span> <span data-ttu-id="3d423-135">這些步驟如下所示：</span><span class="sxs-lookup"><span data-stu-id="3d423-135">These steps are as follows:</span></span>

  - <span data-ttu-id="3d423-136">變更預設的 TCP/IP 通訊協定值。</span><span class="sxs-lookup"><span data-stu-id="3d423-136">Change the Default TCP/IP Protocol Values.</span></span>

  - <span data-ttu-id="3d423-137">建立及設定 SQL Server 別名。</span><span class="sxs-lookup"><span data-stu-id="3d423-137">Create and Configure a SQL Server Alias.</span></span>

  - <span data-ttu-id="3d423-138">建立網域名稱系統（DNS）正式名稱（CNAME）資源記錄。</span><span class="sxs-lookup"><span data-stu-id="3d423-138">Create a Domain Name System (DNS) Canonical Name (CNAME) Resource Record.</span></span>

<span data-ttu-id="3d423-139">**修改預設的 TCP/IP 通訊協定值**</span><span class="sxs-lookup"><span data-stu-id="3d423-139">**Modify the Default TCP/IP Protocol Values**</span></span>

1.  <span data-ttu-id="3d423-140">選取 [**開始**]，然後選擇 [ **SQL Server Configuration Manager**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="3d423-140">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3d423-141">Sql ![Server Management studio 圖示](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "是 Sql server management studio 圖示")</span><span class="sxs-lookup"><span data-stu-id="3d423-141">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="3d423-142">在 [功能窗格] 中，選擇展開 [ **sql server 實例**]，選擇展開 **[sql server Network Configuration**]，然後選擇 [ \*\* \<實例名稱\>的協定\*\*]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="3d423-142">In the navigation pane, choose to expand the **SQL Server instance**, choose to expand **SQL Server Network Configuration**, and choose **Protocols for \<instance name\>**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3d423-143">[![流覽到 Tcp/ip 屬性]] 流覽(images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "至 [tcp/ip 屬性")]</span><span class="sxs-lookup"><span data-stu-id="3d423-143">![Navigate to TCP/IP Properties](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navigate to TCP/IP Properties")</span></span>

3.  <span data-ttu-id="3d423-144">在右窗格中，以滑鼠右鍵按一下 [ **tcp/ip**]，然後選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="3d423-144">In the right pane, right-click **TCP/IP**, and select **Properties**.</span></span> <span data-ttu-id="3d423-145">隨即會顯示 [TCP/IP 屬性] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="3d423-145">The TCP/IP Properties dialog box is displayed.</span></span>

4.  <span data-ttu-id="3d423-146">選取 [ **IP 位址**] 索引標籤。[IP 位址] 索引標籤會顯示伺服器上所有作用中的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3d423-146">Select the **IP Addresses** tab. The IP Addresses tab shows all of the active IP addresses on the server.</span></span> <span data-ttu-id="3d423-147">這些都是以 IP1、IP2、向上至 IPAll 的格式，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="3d423-147">These are in the format IP1, IP2, up to IPAll, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3d423-148">![開啟 [tcp/ip 屬性]。](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "開啟 [tcp/ip 屬性]。")</span><span class="sxs-lookup"><span data-stu-id="3d423-148">![Open TCP/IP properties.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Open TCP/IP properties.")</span></span>

5.  <span data-ttu-id="3d423-149">清除所有 IP 位址的 [ **TCP 動態埠**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="3d423-149">Clear the **TCP Dynamic Ports** field for all IP addresses.</span></span> <span data-ttu-id="3d423-150">如果欄位包含零字元，則表示 SQL Server 正在偵聽動態埠。</span><span class="sxs-lookup"><span data-stu-id="3d423-150">If the field contains a zero character, then it means SQL Server is listening on dynamic ports.</span></span> <span data-ttu-id="3d423-151">請確定這些欄位已清除且不包含零。</span><span class="sxs-lookup"><span data-stu-id="3d423-151">Make sure these fields are cleared and do not contain a zero.</span></span>

6.  <span data-ttu-id="3d423-152">針對 Lync Server 將用來連線至資料庫的 IP 位址，請確定 [**啟用**] 已設定為 **[是]**，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="3d423-152">For the IP address that Lync Server will be using to connect to the database, make sure that **Enabled** is set to **Yes**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3d423-153">![針對正確的 IP 將 [已啟用] 設定為 [是]。](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "針對正確的 IP 將 [已啟用] 設定為 [是]。")</span><span class="sxs-lookup"><span data-stu-id="3d423-153">![Set enabled as Yes for the correct IP.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Set enabled as Yes for the correct IP.")</span></span>

7.  <span data-ttu-id="3d423-154">在對話方塊底部的 [ **IPAll** ] 區段中，于 [ **TCP 埠**] 欄位中輸入想要的埠，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="3d423-154">In the **IPAll** section at the bottom of the dialog, enter the desired port in the **TCP Port** field, as shown in the following figure.</span></span> <span data-ttu-id="3d423-155">在這個範例中，我們使用埠50062，但您可以在49152和65535之間使用任何埠。</span><span class="sxs-lookup"><span data-stu-id="3d423-155">In this example, we use port 50062, but you can use any port between 49152 and 65535.</span></span> <span data-ttu-id="3d423-156">這些是指派給動態及私用的埠，這可確保您不會與 Lync Server 2013 部署中使用的其他埠發生衝突。</span><span class="sxs-lookup"><span data-stu-id="3d423-156">These are the ports assigned to dynamic and private use, and this ensures you won’t conflict with other ports being used in the Lync Server 2013 deployment.</span></span>
    
    <span data-ttu-id="3d423-157">![在 [IPAll] 區段中設定埠。](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "在 [IPAll] 區段中設定埠。")</span><span class="sxs-lookup"><span data-stu-id="3d423-157">![Set port in IPAll section.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Set port in IPAll section.")</span></span>

8.  <span data-ttu-id="3d423-158">選擇 **[確定]** 結束 [tcp/ip 屬性] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="3d423-158">Choose **OK** to exit the TCP/IP Properties dialog.</span></span>

9.  <span data-ttu-id="3d423-159">在 [SQL Server 設定管理員] 的左窗格中選取 **[Sql Server Services** ]，以重新開機 sql server 實例。</span><span class="sxs-lookup"><span data-stu-id="3d423-159">Restart the SQL Server instance by selecting **SQL Server Services** in the left pane of SQL Server Configuration Manager.</span></span> <span data-ttu-id="3d423-160">然後在右窗格中，以滑鼠右鍵按一下 **[SQL Server \<實例\>名稱**]，然後選取 [**重新開機**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="3d423-160">Then right-click **SQL Server \<instance name\>** in the right pane, and select **Restart**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3d423-161">![重設 SQL Server 服務以取得實例。](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "重設 SQL Server 服務以取得實例。")</span><span class="sxs-lookup"><span data-stu-id="3d423-161">![Reset the SQL Server service for instance.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Reset the SQL Server service for instance.")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3d423-162">請確定您更新了防火牆設定，以適應新的 SQL Server 埠。</span><span class="sxs-lookup"><span data-stu-id="3d423-162">Make sure you update your firewall settings to accommodate the new SQL Server port.</span></span>



</div>

<span data-ttu-id="3d423-163">**建立及設定 SQL Server 別名**</span><span class="sxs-lookup"><span data-stu-id="3d423-163">**Create and Configure a SQL Server Alias**</span></span>

1.  <span data-ttu-id="3d423-164">選取 [**開始**]，然後選擇 [ **SQL Server Configuration Manager**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="3d423-164">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3d423-165">Sql ![Server Management studio 圖示](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "是 Sql server management studio 圖示")</span><span class="sxs-lookup"><span data-stu-id="3d423-165">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="3d423-166">在左窗格中，選擇展開 **[Sql Server 實例**]，選擇展開 **[Sql 原\<生\>用戶端版本配置**]，然後選擇 [**別名**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="3d423-166">In the left pane, choose to expand **SQL Server instance**, choose to expand **SQL Native Client \<version\> Configuration**, and then choose **Aliases**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3d423-167">![[SQL Server Configuration Manager] 中的別名。](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "[SQL Server Configuration Manager] 中的別名。")</span><span class="sxs-lookup"><span data-stu-id="3d423-167">![Aliases in SQL Server Configuration Manager.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliases in SQL Server Configuration Manager.")</span></span>

3.  <span data-ttu-id="3d423-168">以滑鼠右鍵按一下 [**別名**]，然後選取 [**新增別名 ...**]。</span><span class="sxs-lookup"><span data-stu-id="3d423-168">Right-click **Aliases**, and select **New Alias…**.</span></span>

4.  <span data-ttu-id="3d423-169">輸入**別名名稱**、**埠號碼**、**通訊協定**和**伺服器**，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="3d423-169">Enter the **Alias Name**, **Port Number**, **Protocol**, and **Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3d423-170">![建立]新的別名以(images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "建立新的別名")</span><span class="sxs-lookup"><span data-stu-id="3d423-170">![Creating a new alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Creating a new alias")</span></span>
    
    <div>
    

    > [!CAUTION]  
    > <span data-ttu-id="3d423-171">請務必輸入您在上一個步驟中所使用的非標準埠，因為這是 SQL Server 要偵聽的埠。</span><span class="sxs-lookup"><span data-stu-id="3d423-171">Make sure to enter the same non-standard port you used in the previous step since that is the port SQL Server will be listening on.</span></span> <span data-ttu-id="3d423-172">如果已設定的別名連線到錯誤的 SQL Server FQDN 或實例，請停用，然後重新啟用相關的網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="3d423-172">If a configured alias is connecting to the wrong SQL Server FQDN or Instance, disable and then re-enable the associated network protocol.</span></span> <span data-ttu-id="3d423-173">這樣做會清除任何快取的連線資訊，並允許用戶端正確連接。</span><span class="sxs-lookup"><span data-stu-id="3d423-173">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>

    
    </div>

<span data-ttu-id="3d423-174">**建立 DNS CNAME 資源記錄**</span><span class="sxs-lookup"><span data-stu-id="3d423-174">**Create a DNS CNAME Resource Record**</span></span>

1.  <span data-ttu-id="3d423-175">登入管理 DNS 的電腦。</span><span class="sxs-lookup"><span data-stu-id="3d423-175">Sign into the computer managing DNS.</span></span>

2.  <span data-ttu-id="3d423-176">選取 [**開始**]，然後選擇 [**伺服器管理員**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="3d423-176">Select **Start**, and choose **Server Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3d423-177">![開啟 Server manager]，(images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "正在開啟伺服器管理員")</span><span class="sxs-lookup"><span data-stu-id="3d423-177">![Opening Server Manager](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Opening Server Manager")</span></span>

3.  <span data-ttu-id="3d423-178">選擇 [**工具**] 下拉式清單，然後選取 [ **DNS**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="3d423-178">Choose the **Tools** drop-down, and select **DNS**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3d423-179">![從伺服器管理員開啟 DNS。](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "從伺服器管理員開啟 DNS。")</span><span class="sxs-lookup"><span data-stu-id="3d423-179">![Opening DNS from Server Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Opening DNS from Server Manager.")</span></span>

4.  <span data-ttu-id="3d423-180">在左窗格中，展開 [伺服器名稱] 節點，展開 [轉寄查閱區域] 節點，然後選擇相關網域。</span><span class="sxs-lookup"><span data-stu-id="3d423-180">In the left pane, expand the server name node, expand the Forward Lookup Zones node, and choose the relevant domain.</span></span>

5.  <span data-ttu-id="3d423-181">以滑鼠右鍵按一下網域，然後選取 **[新增別名（CNAME） ...**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="3d423-181">Right-click the domain, and select **New Alias (CNAME)…**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3d423-182">![選取選項以建立新的別名 cname](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "選取選項以建立新的別名 cname")</span><span class="sxs-lookup"><span data-stu-id="3d423-182">![Selecting option to create a new alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selecting option to create a new alias CNAME")</span></span>

6.  <span data-ttu-id="3d423-183">輸入**別名名稱**和**SQL Server 的 FQDN**，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="3d423-183">Enter the **Alias Name** and the **FQDN for SQL Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3d423-184">![填入 [新的別名 CNAME] 對話方塊。](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "填入 [新的別名 CNAME] 對話方塊。")</span><span class="sxs-lookup"><span data-stu-id="3d423-184">![Filling in the new alias CNAME dialog.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Filling in the new alias CNAME dialog.")</span></span>

7.  <span data-ttu-id="3d423-185">選擇 **[確定]** 以儲存 CNAME，並在 DNS 管理員中加以查看。</span><span class="sxs-lookup"><span data-stu-id="3d423-185">Choose **OK** to save the CNAME and view it in DNS Manager.</span></span>

</div>

<div>

## <a name="validate-database-connectivity"></a><span data-ttu-id="3d423-186">驗證資料庫連線性</span><span class="sxs-lookup"><span data-stu-id="3d423-186">Validate Database Connectivity</span></span>

<span data-ttu-id="3d423-187">有許多不同的方法可確保它能正常運作。</span><span class="sxs-lookup"><span data-stu-id="3d423-187">There are many different ways to make sure it is working.</span></span> <span data-ttu-id="3d423-188">您想要確認 SQL Server 資料庫使用別名來偵聽指定的埠。</span><span class="sxs-lookup"><span data-stu-id="3d423-188">You want to make sure that the SQL Server database is listening on the specified port using the alias.</span></span> <span data-ttu-id="3d423-189">您可以使用**netstat**和**telnet**命令來完成快速檢查。</span><span class="sxs-lookup"><span data-stu-id="3d423-189">A quick check can be completed using the **netstat** and **telnet** commands.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3d423-190">[Telnet 用戶端] 是 Windows Server 隨附的功能，但必須安裝。</span><span class="sxs-lookup"><span data-stu-id="3d423-190">Telnet Client is a Feature that comes with Windows Server but that must be installed.</span></span> <span data-ttu-id="3d423-191">您可以開啟伺服器管理員，然後從 [管理] 功能表中選取 [新增角色和功能]，以安裝 Windows Server 功能。</span><span class="sxs-lookup"><span data-stu-id="3d423-191">A Windows Server Feature can be installed by opening Server Manager and selecting Add Roles and Features from the Manage menu.</span></span>



</div>

<span data-ttu-id="3d423-192">**使用 netstat 和 telnet 驗證資料庫連線性**</span><span class="sxs-lookup"><span data-stu-id="3d423-192">**Use netstat and telnet to verify database connectivity**</span></span>

1.  <span data-ttu-id="3d423-193">選取 [**開始**]，然後輸入**cmd**來開啟命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="3d423-193">Select **Start**, and type **cmd** to open a command prompt.</span></span>

2.  <span data-ttu-id="3d423-194">鍵入**netstat-a-f**，然後確認 SQL Server 使用正確的埠執行，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="3d423-194">Type **netstat -a -f**, and confirm that SQL Server is running with the correct port, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3d423-195">![使用 netstat 驗證埠。](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "使用 netstat 驗證埠。")</span><span class="sxs-lookup"><span data-stu-id="3d423-195">![Using netstat to verify port.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Using netstat to verify port.")</span></span>

3.  <span data-ttu-id="3d423-196">輸入 **[ \<telnet 別名\> \<名稱\#埠**]，確認連線至 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="3d423-196">Type **telnet \<alias name\> \<port \#\>** to confirm the connection to the SQL Server instance.</span></span> <span data-ttu-id="3d423-197">如果連線成功，telnet 會連線，而且您不應該看到錯誤。</span><span class="sxs-lookup"><span data-stu-id="3d423-197">If the connection is successful, telnet will connect and you shouldn’t see an error.</span></span> <span data-ttu-id="3d423-198">這表示 SQL Server 實例正在使用正確的別名來偵聽正確的埠。</span><span class="sxs-lookup"><span data-stu-id="3d423-198">This shows that the SQL Server instance is listening on the correct port with the correct alias.</span></span> <span data-ttu-id="3d423-199">如果連接至 SQL Server 資料庫時發生問題，telnet 會顯示無法建立連線的錯誤。</span><span class="sxs-lookup"><span data-stu-id="3d423-199">If there’s a problem connecting to the SQL Server database, then telnet shows an error that the connection cannot be made.</span></span> <span data-ttu-id="3d423-200">現在您已在資料庫伺服器上檢查資料庫連線，您可以從 Lync Server （透過網路）執行相同的動作，並確定沒有任何防火牆封鎖存取。</span><span class="sxs-lookup"><span data-stu-id="3d423-200">Now that you have checked database connectivity on the database server, you can do the same thing from Lync Server (over the network) and make sure there aren’t any firewalls blocking access along the way.</span></span>

</div>

<div>

## <a name="conclusion"></a><span data-ttu-id="3d423-201">總結</span><span class="sxs-lookup"><span data-stu-id="3d423-201">Conclusion</span></span>

<span data-ttu-id="3d423-202">一旦設定 SQL Server 別名之後，您就可以使用它在拓撲建立器工具中建立 Lync Server 2013 拓撲。</span><span class="sxs-lookup"><span data-stu-id="3d423-202">Once the SQL Server alias has been configured, you can use it to create a Lync Server 2013 topology in the Topology Builder tool.</span></span> <span data-ttu-id="3d423-203">如需有關拓撲的詳細資訊，請參閱[在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="3d423-203">For more information about topologies, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3d423-204">請參閱</span><span class="sxs-lookup"><span data-stu-id="3d423-204">See Also</span></span>


<span data-ttu-id="3d423-205">[Microsoft lync server 2013](microsoft-lync-server-2013.md) 
[規劃 Lync server 2013 中的安全性](lync-server-2013-planning-for-security.md)</span><span class="sxs-lookup"><span data-stu-id="3d423-205">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[Planning for security in Lync Server 2013](lync-server-2013-planning-for-security.md)</span></span>  
[<span data-ttu-id="3d423-206">在 Lync Server 2013 中定義和設定拓撲</span><span class="sxs-lookup"><span data-stu-id="3d423-206">Defining and configuring the topology in Lync Server 2013</span></span>](lync-server-2013-defining-and-configuring-the-topology.md)  
[<span data-ttu-id="3d423-207">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d423-207">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

