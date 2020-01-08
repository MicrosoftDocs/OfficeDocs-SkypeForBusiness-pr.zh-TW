---
title: Lync Server 2013：在拓撲建立器中定義中繼伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f1356217b9effe3f2282f6931b601e84aa46770
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a>在 Lync Server 2013 的拓撲產生器中定義中繼伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-25_

請依照本主題中的步驟，使用拓撲 Builder 來定義獨立的中繼伺服器，或在您先前沒有部署企業語音的網站上使用 [collocated] 池。

您可以使用系統管理員群組成員的帳戶來定義拓撲。

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a>定義轉送伺服器 collocated 到前端池

請依照本主題中的步驟，使用拓撲建立器，在尚未部署企業語音的網站中，將中繼伺服器 collocated 定義為 [前端] 池。

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>將中繼伺服器新增到前端池

1.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

2.  在拓撲建立器中，在主控台樹狀結構中，展開您要為其定義前端池的網站名稱。

3.  在主控台樹狀結構中，以滑鼠右鍵按一下您想要的前端池類型，然後按一下 [**新增前端池 ...**]。

4.  流覽 [**定義新的前臺端池**] 嚮導，直到您到達 [**選取 collocated 伺服器角色**] 頁面。

5.  在 [**選取 collocated 伺服器角色**] 中，核取 [ **Collocate 中繼伺服器**] 的選項。
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>如果您選取的 [前端] 池類型是 [企業版]，則會將轉送伺服器元件安裝在該前端池的所有前端伺服器上。</P>
    > <LI>
    > <P>中繼伺服器所使用的<STRONG>下一個躍點池</STRONG>將是中繼伺服器正在 Collocated 的前端池。</P>
    > <LI>
    > <P>中繼伺服器所使用的<STRONG>邊緣池</STRONG>將是與中繼伺服器所 Collocated 之前端池相關聯的同一個 edge 池。</P></LI></UL>

    
    </div>

6.  按一下 [**設為預設值**]，使用此前端池將來自 Microsoft Office 通訊伺服器 2007 R2 的呼叫路由至 PSTN。

7.  當您完成將一或多個對等專案關聯到前端池之後，按一下 **[完成]** 。
    
    <div>
    

    > [!NOTE]  
    > 在您繼續進行企業語音部署程式中的下一個步驟之前，請確認已將中繼伺服器池（例如，擁有中繼伺服器元件 collocated 的前臺端池）使用您所指定的 Fqdn。

    
    </div>

8.  接著，遵循在[Lync server 2013 中發佈拓撲](lync-server-2013-publish-the-topology.md)中的程式，在 [部署指南] 檔中，將轉送伺服器新增到您的拓撲，然後再繼續進行下一個修改中繼伺服器的偵聽埠（如有需要）。 您必須在每次使用 [拓撲建立器] 定義或修改拓撲時發佈您的拓撲。

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a>定義獨立的中繼伺服器

請依照本主題中的步驟，使用拓撲建立器，在尚未預先部署企業語音的網站上定義獨立的中繼伺服器或池。

如果您已在此網站上將已部署的轉送伺服器 collocated 到前端池，您可以略過此區段，並[在 Lync server 2013 中安裝用於轉送服務伺服器](lync-server-2013-install-the-files-for-mediation-server.md)的檔案，然後再繼續[在 lync server 2013 中設定 trunks](lync-server-2013-configuring-trunks.md)。

<div>


> [!NOTE]  
> 本節假設您已安裝至少一個前端池，如在<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 定義及設定前端池或標準版伺服器中</A>所述，並在部署指南檔中<A href="lync-server-2013-publish-the-topology.md">發佈 lync server 2013 中的拓撲</A>。



</div>

<div>

## <a name="to-add-a-mediation-server"></a>新增中繼伺服器

1.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

2.  在拓撲建立器中，在主控台樹狀結構中，展開您要定義轉送伺服器的網站名稱。

3.  在主控台樹中，以滑鼠右鍵按一下 [**轉送緩衝集區**] 節點，然後按一下 [**轉送伺服器池**]。

4.  在 [**定義新的仲介池**] 中，輸入中繼伺服器池的完整功能變數名稱（FQDN）。

5.  接著，請執行下列其中一項操作：
    
      - 如果您想要在池中部署多個轉送伺服器來提供高可用性，請選取 [**多個電腦池**]。
        
        <div>
        

        > [!NOTE]  
        > 您必須部署 DNS 負載平衡，以支援擁有多個轉送伺服器的中繼伺服器池。 如需詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-dns-load-balancing.md">Lync server 2013</A>中的 [在中繼伺服器池中使用 Dns 負載平衡] 區段。

        
        </div>
    
      - 如果您只想在池中部署一個轉送伺服器，因為您不需要高可用性，請選取 [**單一電腦池**]。 略過下列步驟。

6.  如果您在上一個步驟中選取了**多個電腦池**，請在 [**定義此池中的電腦**] 專案中，按一下 [**電腦 FQDN**]，輸入池中每個伺服器的 FQDN，然後按一下 [**新增**]。 針對您要新增至池中的所有其他轉送伺服器，重複此步驟。 在池中定義所有電腦之後，請按 **[下一步]**。

7.  在 [**選取下一個躍點]** 頁面上，按一下 **[下一個躍點池]**，然後按一下將使用此中繼伺服器池的前端池 FQDN，然後按 **[下一步]**。

8.  在 [**選取邊緣伺服器**] 頁面上，執行下列其中一項操作：
    
      - 如果您想要提供支援企業語音的 PSTN 連線，請在 [**選取此中繼伺服器所使用的 Edge 池**] 底下，按一下將使用此轉送服務伺服器池的 edge 伺服器池，然後按 **[下一步]**。
    
      - 如果您不打算為企業語音啟用外部使用者，或者如果您不想在內部網路外部向使用者提供 PSTN 連線，請按 **[下一步]**。

9.  接著，按照在您的部署檔中[發佈 Lync server 2013](lync-server-2013-publish-the-topology.md)中的拓撲中的程式，將轉送伺服器新增到拓撲。 您必須在每次使用 [拓撲建立器] 建立或修改拓撲時發佈拓撲，才能使用資料來安裝執行 Lync Server 的伺服器的檔案。 然後，繼續進行後續步驟來修改中繼伺服器上的偵聽埠（如有需要）。

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a>定義中繼伺服器偵聽埠

請依照本主題中的步驟，使用拓撲建立器定義中繼伺服器或池將接受來自閘道對等傳入連線的偵聽埠。

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a>修改中繼伺服器偵聽埠

1.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

2.  在 [拓撲建立器] 中，展開 [**轉送緩衝集區**] 節點，然後以滑鼠右鍵按一下先前建立的中繼伺服器。

3.  根據預設，在中繼伺服器上的 SIP 偵聽埠是來自 Lync Server 的 TLS 流量5070，從對等（閘道、PBXes 或 SBCs）進行 TLS 流量的5067。 TCP 埠預設為停用。 如果您的閘道不支援 TLS，您就必須啟用 TCP 埠。

4.  指定所需的 TLS 或 TCP 偵聽埠範圍，中繼伺服器將接受 PSTN 閘道的傳入連線。
    
    <div>
    

    > [!NOTE]  
    > 如果沒有核取 [<STRONG>啟用 tcp 埠</STRONG>]，則不需要輸入 tcp 埠範圍。 此設定是選擇性的。

    
    </div>

接下來，在[Lync server 2013 的拓撲建立器中定義閘道](lync-server-2013-define-a-gateway-in-topology-builder.md)，然後按照在[Lync Server 2013 中安裝轉送伺服器](lync-server-2013-install-the-files-for-mediation-server.md)的檔案中的程式，在池中的每個中繼伺服器上安裝檔案。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

