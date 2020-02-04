---
title: 在 Lync Server 2013  中部署 SQL Server 非標準連接埠和別名
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
ms.openlocfilehash: fffa3502b04a9d05387cd94e157ed183e1fe32ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a>在 Lync Server 2013  中部署 SQL Server 非標準連接埠和別名

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-09-16_

Microsoft Lync Server 2013 支援在 SQL Server 中使用非標準埠和別名。 使用 SQL Server 非標準埠和別名可提高安全性，並為 Lync 部署建立更具彈性的環境。 這些步驟僅適用于適當地保護 Lync Server 2013 環境的單一步驟。 若要減少 Lync Server 2013 實現的受攻擊面，請採取其他步驟。

下列文章說明在 Lync Server 2013 中設定 SQL Server 非標準埠和別名所需的步驟。

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a>在 Lync Server 2013 中部署 SQL Server 非標準埠和別名

Lync Server 2013 拓撲建立器支援使用 SQL Server 別名作為完整功能變數名稱（FQDN），而不是在設定 Lync Server 2013 時實際的 SQL Server FQDN。 這可讓任何惡意攻擊者都能隱藏實際的 SQL Server FQDN。 此外，使用非標準埠掩蓋實際的埠，因為攻擊者試圖在標準埠1433上攻擊資料庫，如下圖所示。

![駭客不知道攻擊的連接埠號碼。](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "駭客不知道攻擊的連接埠號碼。")

若要成功判斷 Lync Server 2013 用來與 SQL Server 通訊的埠，攻擊者需要掃描所有埠以取得埠資訊。 由攻擊者進行的埠掃描可提高安全性檢測並停止指示的機會。 除了使用非標準埠增加安全性之外，您也可以使用 SQL Server 別名來提供部署的彈性。 此功能可讓您在需要變更 SQL Server 名稱的情況下，減少設定變更的價值。

<div>


> [!NOTE]  
> SQL Server 提供兩種容錯方法（容錯移轉叢集及鏡像）。 在 Lync Server 2013 使用 SQL Server 非標準埠和別名，支援這兩種 SQL Server 容錯方法。 如果該池使用的 SQL Server 後端是在鏡像設定中，則 SQL Server 後端伺服器上的 SQL 瀏覽器服務應該在資料庫發生故障時，連線到鏡像資料庫，以便連線到鏡像的 SQL伺服器.



</div>

從拓撲建立器中設定 SQL Server 資料庫連線，或使用 CsDatabase Cmdlet 時，無法明確定義 SQL Server 非標準埠編號，並將它與 SQL 實例建立關聯。 若要設定非標準埠，您必須使用 SQL Server 和 Windows Server 實用程式。

若要設定與 Lync Server 2013 搭配使用的 SQL Server 非標準埠和別名，您必須完成三個主要步驟。 這些步驟如下：

  - 確認 Lync Server 2013 已套用最新的更新。

  - 設定 SQL Server 非標準埠和別名。

  - 使用 [拓撲建立器] 來設定 Lync Server 2013 與 SQL Server 別名。

  - 發佈拓撲結構，並驗證資料庫。

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a>確認 Lync Server 2013 已套用最新的更新

請務必將 Lync Server 2013 保持在最新狀態。 若要查看最新的更新及如何套用的相關資訊，請參閱[Lync Server 2013 更新](http://support.microsoft.com/kb/2809243)。

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a>設定 SQL Server 非標準埠和別名

您必須先在資料庫實例上設定 SQL Server 非標準埠和別名，才能從 Lync Server 2013 拓撲產生器引用它。 若要設定 SQL Server 非標準埠和別名，您必須完成三個主要步驟。 這些步驟如下所示：

  - 變更預設的 TCP/IP 通訊協定值。

  - 建立及設定 SQL Server 別名。

  - 建立網域名稱系統（DNS）正式名稱（CNAME）資源記錄。

**修改預設的 TCP/IP 通訊協定值**

1.  選取 [**開始**]，然後選擇 [ **SQL Server Configuration Manager**]，如下圖所示。
    
    ![SQL Server Management Studio 圖示](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio 圖示")

2.  在 [功能窗格] 中，選擇展開 [ **sql server 實例**]，選擇展開 **[sql server Network Configuration**]，然後選擇 [ ** \<實例名稱\>的協定**]，如下圖所示。
    
    ![瀏覽至 TCP/IP 內容](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "瀏覽至 TCP/IP 內容")

3.  在右窗格中，以滑鼠右鍵按一下 [ **tcp/ip**]，然後選取 [**屬性**]。 隨即會顯示 [TCP/IP 屬性] 對話方塊。

4.  選取 [ **IP 位址**] 索引標籤。[IP 位址] 索引標籤會顯示伺服器上所有作用中的 IP 位址。 這些都是以 IP1、IP2、向上至 IPAll 的格式，如下圖所示。
    
    ![開啟 TCP/IP 內容。](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "開啟 TCP/IP 內容。")

5.  清除所有 IP 位址的 [ **TCP 動態埠**] 欄位。 如果欄位包含零字元，則表示 SQL Server 正在偵聽動態埠。 請確定這些欄位已清除且不包含零。

6.  針對 Lync Server 將用來連線至資料庫的 IP 位址，請確定 [**啟用**] 已設定為 **[是]**，如下圖所示。
    
    ![請將正確 IP 的啟用設為 [是]。](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "請將正確 IP 的啟用設為 [是]。")

7.  在對話方塊底部的 [ **IPAll** ] 區段中，于 [ **TCP 埠**] 欄位中輸入想要的埠，如下圖所示。 在這個範例中，我們使用埠50062，但您可以在49152和65535之間使用任何埠。 這些是指派給動態及私用的埠，這可確保您不會與 Lync Server 2013 部署中使用的其他埠發生衝突。
    
    ![設定 IPAll 區段的連接埠。](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "設定 IPAll 區段的連接埠。")

8.  選擇 **[確定]** 結束 [tcp/ip 屬性] 對話方塊。

9.  在 [SQL Server 設定管理員] 的左窗格中選取 **[Sql Server Services** ]，以重新開機 sql server 實例。 然後在右窗格中，以滑鼠右鍵按一下 **[SQL Server \<實例\>名稱**]，然後選取 [**重新開機**]，如下圖所示。
    
    ![針對執行個體重設 SQL Server 服務。](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "針對執行個體重設 SQL Server 服務。")

<div>


> [!IMPORTANT]  
> 請確定您更新了防火牆設定，以適應新的 SQL Server 埠。



</div>

**建立及設定 SQL Server 別名**

1.  選取 [**開始**]，然後選擇 [ **SQL Server Configuration Manager**]，如下圖所示。
    
    ![SQL Server Management Studio 圖示](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio 圖示")

2.  在左窗格中，選擇展開 **[Sql Server 實例**]，選擇展開 **[Sql 原\<生\>用戶端版本配置**]，然後選擇 [**別名**]，如下圖所示。
    
    ![SQL Server 組態管理員中的別名。](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "SQL Server 組態管理員中的別名。")

3.  以滑鼠右鍵按一下 [**別名**]，然後選取 [**新增別名 ...**]。

4.  輸入**別名名稱**、**埠號碼**、**通訊協定**和**伺服器**，如下圖所示。
    
    ![建立新別名](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "建立新別名")
    
    <div>
    

    > [!CAUTION]  
    > 請務必輸入您在上一個步驟中所使用的非標準埠，因為這是 SQL Server 要偵聽的埠。 如果已設定的別名連線到錯誤的 SQL Server FQDN 或實例，請停用，然後重新啟用相關的網路通訊協定。 這樣做會清除任何快取的連線資訊，並允許用戶端正確連接。

    
    </div>

**建立 DNS CNAME 資源記錄**

1.  登入管理 DNS 的電腦。

2.  選取 [**開始**]，然後選擇 [**伺服器管理員**]，如下圖所示。
    
    ![開啟伺服器管理員](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "開啟伺服器管理員")

3.  選擇 [**工具**] 下拉式清單，然後選取 [ **DNS**]，如下圖所示。
    
    ![從伺服器管理員開啟 DNS。](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "從伺服器管理員開啟 DNS。")

4.  在左窗格中，展開 [伺服器名稱] 節點，展開 [轉寄查閱區域] 節點，然後選擇相關網域。

5.  以滑鼠右鍵按一下網域，然後選取 **[新增別名（CNAME） ...**]，如下圖所示。
    
    ![選取選項來建立新別名 CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "選取選項來建立新別名 CNAME")

6.  輸入**別名名稱**和**SQL Server 的 FQDN**，如下圖所示。
    
    ![填寫新別名 CNAME 對話方塊。](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "填寫新別名 CNAME 對話方塊。")

7.  選擇 **[確定]** 以儲存 CNAME，並在 DNS 管理員中加以查看。

</div>

<div>

## <a name="validate-database-connectivity"></a>驗證資料庫連線性

有許多不同的方法可確保它能正常運作。 您想要確認 SQL Server 資料庫使用別名來偵聽指定的埠。 您可以使用**netstat**和**telnet**命令來完成快速檢查。

<div>


> [!NOTE]  
> [Telnet 用戶端] 是 Windows Server 隨附的功能，但必須安裝。 您可以開啟伺服器管理員，然後從 [管理] 功能表中選取 [新增角色和功能]，以安裝 Windows Server 功能。



</div>

**使用 netstat 和 telnet 驗證資料庫連線性**

1.  選取 [**開始**]，然後輸入**cmd**來開啟命令提示字元。

2.  鍵入**netstat-a-f**，然後確認 SQL Server 使用正確的埠執行，如下圖所示。
    
    ![使用 netstat 驗證連接埠。](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "使用 netstat 驗證連接埠。")

3.  輸入 **[ \<telnet 別名\> \<名稱\#埠**]，確認連線至 SQL Server 實例。 如果連線成功，telnet 會連線，而且您不應該看到錯誤。 這表示 SQL Server 實例正在使用正確的別名來偵聽正確的埠。 如果連接至 SQL Server 資料庫時發生問題，telnet 會顯示無法建立連線的錯誤。 現在您已在資料庫伺服器上檢查資料庫連線，您可以從 Lync Server （透過網路）執行相同的動作，並確定沒有任何防火牆封鎖存取。

</div>

<div>

## <a name="conclusion"></a>總結

一旦設定 SQL Server 別名之後，您就可以使用它在拓撲建立器工具中建立 Lync Server 2013 拓撲。 如需有關拓撲的詳細資訊，請參閱[在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。

</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[Microsoft lync server 2013](microsoft-lync-server-2013.md) 
[規劃 Lync server 2013 中的安全性](lync-server-2013-planning-for-security.md)  
[在 Lync Server 2013 中定義和設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)  
[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

