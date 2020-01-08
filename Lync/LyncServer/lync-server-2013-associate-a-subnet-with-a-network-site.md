---
title: Lync Server 2013：建立子網路與網路站台的關聯
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec5a896af6312fecf53259ac10e72f99598d4a7e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a>在 Lync Server 2013 中建立子網路與網路站台的關聯

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

您網路中的每個子網都必須與特定的網路網站相關聯，因為子網資訊是用來判斷在啟動新的會話時，端點所在的網路網站。 當會話中每一方的位置已知時，高級企業語音功能可以套用該資訊來決定如何處理通話設定或路由。

<div>


> [!IMPORTANT]  
> 您必須將部署中音訊/視頻邊緣伺服器的所有已設定公用 IP 位址新增至您的網路設定。 這些 IP 位址會新增成遮罩為32的子網。 相關的網路網站應該對應至適當設定的網路網站。 例如，與中央網站芝加哥的 A/V 邊緣伺服器相對應的公用 IP 位址為 NetworkSiteID 芝加哥。 如需有關公用 IP 位址的詳細資料，請參閱在規劃檔中，針對<A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Lync Server 2013 判斷外部 A/V 防火牆和埠需求</A>。



</div>

<div>


> [!NOTE]  
> 會產生一個金鑰健康情況指標（KHI）警示，指定您網路中存在的 IP 位址清單，但不與子網建立關聯，或者包含 IP 位址的子網不與網路網站產生關聯。 在8小時內，不會多次引發此通知。 相關的警示資訊和範例如下所示：<BR><STRONG>來源：</STRONG>CS 頻寬原則服務（核心）<BR><STRONG>事件號碼：</STRONG> 36034<BR><STRONG>層級：</STRONG> 2<BR><STRONG>描述：</STRONG>下列 IP 位址的子網： &lt;ip 位址&gt;清單未設定，或子網不與網路網站相關聯。<BR><STRONG>原因：</STRONG>[網路設定] 中缺少對應 IP 位址的子網，或子網不會與網路網站產生關聯。<BR><STRONG>解決方式：</STRONG>將對應至 IP 位址清單的子網新增至 [網路設定]，並將每個子網與網路網站建立關聯。<BR>例如，如果警示中的 IP 位址清單指定10.121.248.226 和10.121.249.20，則這些 IP 位址不會與子閘道聯，或與其相關聯的子網不屬於網路網站。 如果 10.121.248.0/24 和 10.121.249.0/24 是這些位址對應的子網，您可以解決此問題，如下所示： 
> <OL>
> <LI>
> <P>請確定 IP 位址10.121.248.226 已與 10.121.249.0/24 子網相關聯的 10.121.248.0/24 子網和 IP 位址10.121.249.20 相關聯。</P>
> <LI>
> <P>請確定 10.121.248.0/24 和 10.121.249.0/24 子網分別與網路網站產生關聯。</P></LI></OL>



</div>

如需使用網路子網的詳細資料，請參閱下列 Cmdlet 的 Lync Server 管理命令介面檔：

  - [新-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [移除-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> 如果您使用的是大量的子網，建議您使用逗號分隔值（CSV）檔案，將子網與網站產生關聯。 CSV 檔案必須具有下列四個數據行： <STRONG>IPAddress</STRONG>、 <STRONG>mask</STRONG>、 <STRONG>description</STRONG>、 <STRONG>NetworkSiteID</STRONG>。



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a>使用管理命令介面將子網與網路網站建立關聯

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行**新的 CsNetworkSubnet** Cmdlet，以將子網與網路網站建立關聯：
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    例如：
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    在這個範例中，您已在子網172.11.12.13 和網路網站 "芝加哥" 之間建立關聯。

3.  針對您的拓撲中的所有子網，重複步驟2。

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>匯入 CSV 檔案以將子網與網路網站建立關聯

1.  建立包含您要新增之所有子網的 CSV 檔案。 例如，建立名為**subnet**的檔案，並提供下列內容：
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  執行下列 Cmdlet 以匯入**子網 .csv**，然後將其內容儲存在 Lync Server 管理儲存區：
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 將子網與網路網站建立關聯

1.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左側導覽列中，按一下 [**網路**設定]。

3.  按一下**子網**導覽按鈕。

4.  按一下 [**新增**]。

5.  在 [**新的子網**] 頁面上，按一下 [**子網識別碼**]，然後在您想要與網路網站建立關聯的子網所定義的 IP 位址範圍中輸入第一個位址。

6.  按一下 [**遮罩**]，然後輸入要套用至子網的位元遮罩。

7.  按一下 [**網路網站識別碼**]，然後選取您要新增此子網的網站的 [網站識別碼]。
    
    <div>
    

    > [!NOTE]  
    > 如果您尚未建立網路網站，此清單將會是空白的。 如需有關程式的詳細資訊，請參閱<A href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync Server 2013 中建立或修改網路網站</A>。 您也可以執行<STRONG>CsNetworkSite</STRONG> Cmdlet，以取得您的部署的網站識別碼。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔。

    
    </div>

8.  或者，按一下 [**描述**]，然後輸入說明這個子網上的其他資訊。

9.  按一下 [認可]****。

重複這些步驟，將其他子網新增至網路網站。

</div>

</div>

<span> </span>

</div>

</div>

</div>

