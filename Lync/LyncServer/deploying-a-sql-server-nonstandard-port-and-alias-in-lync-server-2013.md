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
ms.openlocfilehash: 51d102c6a810730d6c748dafc6a4fcdc3dd6821e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a>在 Lync Server 2013 中部署 SQL Server 非標準埠和別名

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-09-16_

Microsoft Lync Server 2013 支援在 SQL Server 中使用非標準埠和別名。 使用 SQL Server 非標準埠和別名可提高安全性，並為 Lync 部署建立更靈活的環境。 這些步驟只是正確保護您的 Lync Server 2013 環境的單一步驟。 您應採取額外的步驟來減少 Lync Server 2013 實施的攻擊面。

下列文章說明在 Lync Server 2013 中安裝 SQL Server 非標準埠和別名所需的步驟。

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a>在 Lync Server 2013 中部署 SQL Server 非標準埠和別名

Lync Server 2013 拓撲產生器支援使用 SQL Server 別名做為完整功能變數名稱 (FQDN) ，而不是在設定 Lync Server 2013 時使用實際的 SQL Server FQDN。 這可讓實際的 SQL Server FQDN 對任何惡意攻擊者隱藏。 此外，使用非標準埠掩蓋實際埠，攻擊者可能會嘗試攻擊標準埠1433上的資料庫，如下圖所示。

![駭客不知道要攻擊的埠號碼。](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "駭客不知道要攻擊的埠號碼。")

為了成功判斷使用的埠 Lync Server 2013 與 SQL Server 通訊，攻擊者必須掃描所有的埠，以取得埠資訊。 攻擊者所進行的埠掃描可提高安全性偵測和停止指示的機會。 除了使用非標準埠新增加強的安全性之外，您也可以使用 SQL Server 別名，為部署提供彈性。 在需要 SQL Server 名稱變更的情況下，這是很有用的，以便減少設定的變更。

<div>


> [!NOTE]  
> SQL Server 提供兩種容錯方法 (容錯移轉叢集及鏡像) 。 使用 SQL Server 非標準埠和具有 Lync Server 2013 的別名，都支援這兩種 SQL Server 容錯方法。 如果集區使用的 SQL Server 後端是在鏡像設定中，則當資料庫容錯移轉至鏡像的 SQL Server 時，應執行 SQL Server 後端伺服器上的 SQL browser 服務，以連線至鏡像資料庫。



</div>

從拓撲產生器內設定 SQL Server 資料庫連線時，或在使用 Install-CsDatabase Cmdlet 時，無法明確定義 SQL Server 非標準埠號碼，並將它與 SQL 實例產生關聯。 若要設定非標準埠，您必須使用 SQL Server 及 Windows Server 公用程式。

若要設定 SQL Server 非標準埠和別名以用於 Lync Server 2013，您將需要完成三個主要步驟。 這些步驟包括：

  - 確認 Lync Server 2013 已套用最新的更新。

  - 設定 SQL Server 非標準埠和別名。

  - 使用拓撲產生器，設定使用 SQL Server 別名的 Lync Server 2013。

  - 發行拓撲，並驗證資料庫。

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a>確認 Lync Server 2013 已套用最新的更新

務必將 Lync Server 2013 保持在最新狀態。 若要檢查最近的更新及如何套用的資訊，請參閱[Lync Server 2013 的更新](https://support.microsoft.com/kb/2809243)。

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a>設定 SQL Server 非標準埠和別名

在資料庫實例上，必須先設定 SQL Server 非標準埠和別名，才能從 Lync Server 2013 拓撲產生器參照它。 若要設定 SQL Server 非標準埠和別名，您必須完成三個主要步驟。 這些步驟如下：

  - 變更預設的通訊協定值 TCP/IP。

  - 建立及設定 SQL Server 別名。

  - 建立網域名稱系統 (DNS) 正常化名稱 (CNAME) 資源記錄。

**修改預設 TCP/IP 通訊協定值**

1.  選取 [**開始**]，然後選擇 [ **SQL Server Configuration Manager**]，如下圖所示。
    
    ![SQL Server Management Studio 圖示](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio 圖示")

2.  在功能窗格中，選擇展開**Sql server 實例**，選擇展開 [ **sql server 網路**設定]，然後選擇 [ ** \< 實例名稱 \> 的通訊協定**]，如下圖所示。
    
    ![流覽至 TCP/IP 屬性](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "流覽至 TCP/IP 屬性")

3.  在右窗格中，以滑鼠右鍵按一下 [ **TCP/IP**]，然後選取 [**屬性**]。 隨即會顯示 [TCP/IP 屬性] 對話方塊。

4.  選取 [ **IP 位址**] 索引標籤。[IP 位址] 索引標籤會顯示伺服器上所有使用中的 IP 位址。 其格式為 IP1，IP2，最多 IPAll，如下圖所示。
    
    ![開啟 TCP/IP 屬性。](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "開啟 TCP/IP 屬性。")

5.  清除所有 IP 位址的 [ **TCP 動態埠**] 欄位。 如果欄位包含零字元，則表示 SQL Server 正在接聽動態埠。 請確定這些欄位已清除，而且不含零。

6.  如需 Lync Server 用來連線至資料庫的 IP 位址，請確定**Enabled**已設定為 **[是]**，如下圖所示。
    
    ![針對正確的 IP，將啟用設為 [是]。](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "針對正確的 IP，將啟用設為 [是]。")

7.  在對話方塊底部的 [ **IPAll** ] 區段中，于 [ **TCP 埠**] 欄位中輸入所需的埠，如下圖所示。 在此範例中，我們使用埠50062，但您可以使用49152和65535之間的任何埠。 這些是指派給動態及私人使用的埠，這可確保您不會與 Lync Server 2013 部署中使用的其他通訊埠產生衝突。
    
    ![在 IPAll 區段中設定埠。](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "在 IPAll 區段中設定埠。")

8.  選擇 **[確定**]，結束 [TCP/IP 屬性] 對話方塊。

9.  在 SQL Server Configuration Manager 的左窗格中，選取 [ **Sql Server 服務**]，以重新開機 sql server 實例。 然後在右窗格中以滑鼠右鍵按一下 **[SQL Server \< 實例名稱 \> ** ]，然後選取 [**重新開機**]，如下圖所示。
    
    ![針對 instance 重設 SQL Server 服務。](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "針對 instance 重設 SQL Server 服務。")

<div>


> [!IMPORTANT]  
> 請確定您更新防火牆設定，以容納新的 SQL Server 埠。



</div>

**建立及設定 SQL Server 別名**

1.  選取 [**開始**]，然後選擇 [ **SQL Server Configuration Manager**]，如下圖所示。
    
    ![SQL Server Management Studio 圖示](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio 圖示")

2.  在左窗格中，選擇展開 **[Sql Server 實例**]，選擇展開 **[sql Native Client \< version \> Configuration**]，然後選擇 [**別名**]，如下圖所示。
    
    ![SQL Server Configuration Manager 中的別名。](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "SQL Server Configuration Manager 中的別名。")

3.  以滑鼠右鍵按一下 [**別名**]，然後選取 [**新增別名 ...**]。

4.  輸入**別名名稱**、**埠號碼**、**通訊協定**和**伺服器**，如下圖所示。
    
    ![建立新的別名](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "建立新的別名")
    
    <div>
    

    > [!CAUTION]  
    > 請務必輸入您在上一個步驟中使用的相同非標準埠，因為這是 SQL Server 將要接聽的埠。 如果已設定的別名連接至錯誤的 SQL Server FQDN 或實例，請停用，然後重新啟用相關聯的網路通訊協定。 這樣做會清除任何快取的連線資訊，並允許用戶端正確連接。

    
    </div>

**建立 DNS CNAME 資源記錄**

1.  登入管理 DNS 的電腦。

2.  選取 [**啟動**]，然後選擇 [**伺服器管理員**]，如下圖所示。
    
    ![開啟伺服器管理員](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "開啟伺服器管理員")

3.  選擇 [**工具**] 下拉式清單，然後選取 [ **DNS**]，如下圖所示。
    
    ![從 [伺服器管理員] 開啟 DNS。](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "從 [伺服器管理員] 開啟 DNS。")

4.  在左窗格中，展開 [伺服器名稱] 節點，展開 [正向對應區域] 節點，然後選擇相關的網域。

5.  在網域上按一下滑鼠右鍵，然後選取 [**新增別名 (CNAME) ...**]，如下圖所示。
    
    ![選取選項以建立新的別名 CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "選取選項以建立新的別名 CNAME")

6.  輸入**別名名稱**和**SQL Server 的 FQDN**，如下圖所示。
    
    ![填入 [新增別名 CNAME] 對話方塊。](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "填入 [新增別名 CNAME] 對話方塊。")

7.  選擇 **[確定]** 以儲存 CNAME 並在 DNS 管理員中查看。

</div>

<div>

## <a name="validate-database-connectivity"></a>驗證資料庫連線能力

有許多不同的方式可確保其正常運作。 您想確定 SQL Server 資料庫正在使用別名在指定的埠上接聽。 您可以使用**netstat**和**telnet**命令來完成快速檢查。

<div>


> [!NOTE]  
> 「Telnet 用戶端」是 Windows Server 附帶但必須安裝的功能。 您可以從 [管理] 功能表中，開啟 [伺服器管理員] 並選取 [新增角色及功能]，即可安裝 Windows Server 功能。



</div>

**使用 netstat 和 telnet 驗證資料庫連線能力**

1.  選取 [**開始**]，然後輸入**cmd**以開啟命令提示字元。

2.  輸入**netstat-a-f**，並確認 SQL Server 正在使用正確的埠執行，如下圖所示。
    
    ![使用 netstat 驗證埠。](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "使用 netstat 驗證埠。")

3.  輸入**telnet \< alias name \> \< port \# \> ** ，以確認 SQL Server 實例的連線。 如果連線成功，telnet 將會連線，而且您不會看到錯誤。 這會顯示 SQL Server 實例正在使用正確的別名在正確的埠上接聽。 如果連線到 SQL Server 資料庫時發生問題，telnet 會顯示無法進行連線的錯誤。 現在，您已在資料庫伺服器上檢查資料庫連線能力，您可以透過網路上的 Lync Server (執行相同的作業) 並確定沒有任何防火牆封鎖存取方式。

</div>

<div>

## <a name="conclusion"></a>總結

在設定 SQL Server 別名之後，您可以在拓撲產生器工具中使用它來建立 Lync Server 2013 拓撲。 如需拓撲的詳細資訊，請參閱[在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。

</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[Microsoft Lync Server 2013](microsoft-lync-server-2013.md)  
[Lync Server 2013 中的安全性規劃](lync-server-2013-planning-for-security.md)  
[在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)  
[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

