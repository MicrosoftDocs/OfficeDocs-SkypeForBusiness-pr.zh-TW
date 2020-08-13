---
title: Lync Server 2013：將子網與網路網站建立關聯
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6d41e5959eaf596faaed25a9759534a9156f0d9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a>在 Lync Server 2013 中建立子網與網路網站的關聯

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

您網路中的每個子網都必須與特定網路網站產生關聯，因為子網資訊是用來決定端點所在的網路網站，而啟動新的會話時。 在會話中每一方的位置已知時，「高級 Enterprise 語音功能」可以套用該資訊，決定如何處理通話設定或路由傳送。

<div>


> [!IMPORTANT]  
> 您部署中 Audio/Video Edge Server 的所有已設定公用 IP 位址，都必須新增至您的網路設定。 這兩個 IP 位址會新增為遮罩為32的子網。 相關聯的網路網站應該對應至適當設定的網站。 例如，與中央網站芝加哥的 A/V Edge Server 對應的公用 IP 位址，將會是 NetworkSiteID 芝加哥。 如需公用 IP 位址的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">決定 Lync Server 2013 的外部 A/V 防火牆和埠需求</A> 。



</div>

<div>


> [!NOTE]  
> 會引發重要狀態指示器 (KHI) 通知，指定存在於您的網路中，但未與子網路相關聯，或包含 IP 位址的子網路未與網站相關聯的 IP 位址清單。 在8小時內，將不會多次引發此警示。 以下是相關的通知資訊與範例：<BR><STRONG>來源：</STRONG> CS 頻寬原則服務 (核心) <BR><STRONG>事件編號：</STRONG> 36034<BR><STRONG>層級：</STRONG> 2<BR><STRONG>描述：</STRONG> 下列 IP 位址的子網： &lt; 未設定 Ip 位址的清單 &gt; ，或未將子網與網路網站產生關聯。<BR><STRONG>原因：</STRONG> 網路設定中遺失對應之 IP 位址的子網，也不會將子網與網路網站產生關聯。<BR><STRONG>解決方法：</STRONG> 將對應至 IP 位址清單的子網新增至網路設定設定，並將每個子網與網站產生關聯。<BR>例如，如果警示中的 IP 位址清單指定10.121.248.226 和10.121.249.20，則這些 IP 位址不會與子網產生關聯，或與其相關聯的子網不屬於網路網站。 如果 10.121.248.0/24 與 10.121.249.0/24 是這些位址的對應子網路，您可以透過下列方式解決此問題： 
> <OL>
> <LI>
> <P>確定 IP 位址 10.121.248.226 與 10.121.248.0/24 子網路相關聯，而 IP 位址 10.121.249.20 與 10.121.249.0/24 子網路相關聯。</P>
> <LI>
> <P>確定 10.121.248.0/24 與 10.121.249.0/24 兩個子網路分別與一個網站相關聯。</P></LI></OL>



</div>

如需使用網路子網的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：

  - [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> 如果您使用的是大量子網，建議您使用以逗號分隔的值 (CSV) 檔案，以將子網與網站產生關聯。 CSV 檔案必須具有下列四個欄： <STRONG>IPAddress</STRONG>、 <STRONG>mask</STRONG>、 <STRONG>description</STRONG>、 <STRONG>NetworkSiteID</STRONG>。



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a>使用管理命令介面建立子網與網路網站的關聯

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 **New-CsNetworkSubnet** Cmdlet 以將子網與網路網站產生關聯：
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    例如：
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    在此範例中，您已建立子網172.11.12.13 與網路網站 "芝加哥" 之間的關聯性。

3.  對拓撲中的所有子網重複步驟2。

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>若要將子網與網站結合匯入 CSV 檔案

1.  建立包含您要新增之所有子網的 CSV 檔案。 例如，使用下列內容建立名為 **subnet.csv** 的檔案：
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  執行下列 Cmdlet 以匯入 **subnet.csv**，然後將其內容儲存在 Lync Server management store 中：
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台建立子網與網路網站的關聯

1.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左導覽列中，按一下 **[網路組態]**。

3.  按一下 [ **子網** ] 導覽按鈕。

4.  按一下 [ **新增**]。

5.  在 [ **新建子網上** ] 頁面上，按一下 [ **子網識別碼**]，然後輸入您要與網路網站建立關聯之子網所定義之 IP 位址範圍中的第一個位址。

6.  按一下 [ **遮罩**]，然後輸入要套用至子網的位元遮罩。

7.  按一下 [ **網路網站識別碼**]，然後選取您要新增此子網的網站的網站識別碼。
    
    <div>
    

    > [!NOTE]  
    > 如果您尚未建立網路網站，此清單將會是空的。 如需程式的詳細資訊，請參閱 <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify network site In Lync Server 2013</A>。 您也可以執行 <STRONG>Get-CsNetworkSite</STRONG> Cmdlet，以取得部署的網站 IDs。 如需詳細資料，請參閱＜Lync Server 管理命令介面＞文件。

    
    </div>

8.  （選用）按一下 [ **描述**]，然後輸入其他資訊以描述這個子網。

9.  按一下 **[認可]**。

重複這些步驟，將其他子網新增至網路網站。

</div>

</div>

<span> </span>

</div>

</div>

</div>

