---
title: Lync Server 2013：在拓撲產生器中定義轉送伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 368dc6d5e19adede1752c148c661c1c04788a9b6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516470"
---
# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a>在 Lync Server 2013 的拓撲產生器中定義轉送伺服器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-25_

遵循此主題中的步驟，使用拓撲產生器來定義獨立的轉送伺服器或集區組合，並在先前未部署 Enterprise Voice 之網站上使用前端集區。

您可以使用屬於 Administrators 群組成員的帳戶來定義拓撲。

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a>定義轉送伺服器組合至前端集區

請遵循本主題中的步驟，使用拓撲產生器，將轉送伺服器組合定義至先前未部署 Enterprise Voice 之網站的前端集區。

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>若要將轉送伺服器新增至前端集區

1.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  在 [拓撲產生器] 的主控台樹中，展開您要定義前端集區的網站名稱。

3.  在主控台樹中，以滑鼠右鍵按一下您想要的前端集區類型，然後按一下 [ **新增前端集**區]。

4.  完整瀏覽 [定義新前端集區]**** 精靈，直到到達 [選取組合的伺服器角色]**** 頁面為止。

5.  在 [ **選取組合伺服器角色**] 中，選取 [ **組合轉送伺服器**] 選項。
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>如果您選取的前端集區類型是 Enterprise Edition，則轉送伺服器元件將會安裝在該前端集區的所有前端伺服器上。</P>
    > <LI>
    > <P>轉送伺服器所使用的 <STRONG>下一個躍點集</STRONG> 區將是轉送伺服器組合所在的前端集區。</P>
    > <LI>
    > <P>轉送伺服器所使用的 <STRONG>edge 集</STRONG> 區將是與組合轉送伺服器的前端集區相關聯的相同 edge 集區。</P></LI></UL>

    
    </div>

6.  按一下 [ **成為預設值** ]，使用此前端集區，將來自 Microsoft Office 通訊伺服器 2007 R2 的呼叫路由傳送至 PSTN。

7.  完成將一或多個對等專案關聯至前端集區時，按一下 **[完成]** 。
    
    <div>
    

    > [!NOTE]  
    > 在繼續進行企業語音部署程式的下一個步驟之前，請確定轉送伺服器集區 (（即「轉送伺服器元件」組合) 的前端集區）是使用您指定的 Fqdn。

    
    </div>

8.  接下來，遵循 [部署指南檔] 中的 [在 [Lync server 2013 中發佈拓撲](lync-server-2013-publish-the-topology.md) ] 中的程式，將轉送伺服器新增至您的拓撲，然後再繼續進行下一個修改轉送伺服器的聆聽埠（如有需要）的步驟。 您必須在每次使用拓撲產生器來定義或修改拓撲時，發行您的拓撲。

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a>定義獨立轉送伺服器

遵循此主題中的步驟，使用拓撲產生器來定義獨立的轉送伺服器或集區，該網站的 Enterprise Voice 先前尚未部署。

如果您已在此網站上部署組合至前端集區的轉送伺服器，則可以略過本節並 [在 Lync server 2013 中安裝轉送伺服器的](lync-server-2013-install-the-files-for-mediation-server.md) 檔案，然後再繼續設定 [lync server 2013 中的主幹](lync-server-2013-configuring-trunks.md)。

<div>


> [!NOTE]  
> 本節假設您已安裝至少一個前端集區（如 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">定義及設定 Lync server 2013 中的前端集區或 Standard Edition server</A> 所述），並在部署指南檔中 <A href="lync-server-2013-publish-the-topology.md">發佈 lync server 2013 中的拓撲</A> 。



</div>

<div>

## <a name="to-add-a-mediation-server"></a>新增中繼伺服器

1.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  在 [拓撲產生器] 的主控台樹中，展開您要定義轉送伺服器的網站名稱。

3.  在主控台樹中，以滑鼠右鍵按一下 **[中繼** 集區] 節點，然後按一下 [ **轉送伺服器集**區]。

4.  在 [ **定義新**的中繼集區] 中，輸入轉送伺服器集區的完整功能變數名稱 (FQDN) 。

5.  接著執行下列其中一項作業：
    
      - 如果您想要在集區中部署多個轉送伺服器以提供高可用性，請選取 [ **多部電腦集**區]。
        
        <div>
        

        > [!NOTE]  
        > 您必須部署 DNS 負載平衡，以支援具有多部轉送伺服器的轉送伺服器集區。 如需詳細資訊，請參閱規劃檔中的在 <A href="lync-server-2013-dns-load-balancing.md">Lync server 2013</A> 中使用 dns 負載平衡的轉送伺服器集區一節。

        
        </div>
    
      - 如果您只想要在集區中部署一個轉送伺服器，因為您不需要高可用性，請選取 [ **單一電腦集**區]。 略過下列步驟。

6.  如果您在上一個步驟中，在 [定義此集區中的電腦]**** 項目上選取了 [多部電腦集區]****，則可按一下 [電腦 FQDN]****、鍵入集區中每一部伺服器的 FQDN，然後按一下 [新增]****。 針對您要新增至集區的所有其他轉送伺服器重複此步驟。 在定義集區中的所有電腦之後，按 [下一步]****。

7.  在 [ **選取下一個躍點]** 頁面上，按一下 **[下一個躍點集區]**，然後按一下將使用此轉送伺服器集區的前端集區 FQDN，然後按 **[下一步]**。

8.  在 **[選取 Edge Server]** 頁面上，執行下列其中一項：
    
      - 如果您想要為已啟用 Enterprise Voice 的外部使用者提供 PSTN 連線，請在 [ **選取此轉送伺服器使用的 Edge 集**區] 下，按一下將使用此轉送伺服器集區的 edge Server 集區 FQDN，以提供 PSTN 連線到這些外部使用者，然後按 **[下一步]**。
    
      - 如果您不打算為外部使用者啟用 Enterprise Voice，或是不想要在內部網路以外為使用者提供 PSTN 連線能力，請按 **[下一步]**。

9.  接下來，遵循在 [部署檔] 中的 [在 [Lync Server 2013 中發佈拓撲](lync-server-2013-publish-the-topology.md) ] 中的程式，將轉送伺服器新增至拓撲。 您必須在每次使用拓撲產生器建立或修改拓撲時發佈拓撲，以便使用資料來安裝執行 Lync Server 之伺服器的檔案。 接著，視需要進行後續步驟，修改中繼伺服器上的聆聽連接埠。

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a>定義轉送伺服器聆聽埠

遵循此主題中的步驟，使用拓撲產生器定義轉送伺服器或集區將接受來自閘道對等的傳入連線的聆聽埠。

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a>修改轉送伺服器的聆聽埠

1.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  在 [拓撲產生器] 的主控台樹中，展開 [中繼集區 **] 節點，** 然後以滑鼠右鍵按一下先前建立的轉送伺服器。

3.  根據預設，轉送伺服器上的 SIP 聆聽埠為5070來自 Lync Server 的 TLS 流量，5067用於來自對等 (閘道、PBXes 或 SBCs) 的 TLS 流量。 TCP 連接埠預設是停用的。 如果您的閘道不支援 TLS，則必須啟用 TCP 連接埠。

4.  指定所需的 TLS 或 TCP 接聽埠範圍，轉送伺服器將接受來自 PSTN 閘道的傳入連線。
    
    <div>
    

    > [!NOTE]  
    > 若未勾選 [啟用 TCP 連接埠]<STRONG></STRONG>，則不一定要輸入 TCP 連接埠範圍。 此為選用設定。

    
    </div>

接下來，在 Lync server 2013 中的拓撲產生器中 [定義閘道](lync-server-2013-define-a-gateway-in-topology-builder.md) ，並遵循在 [lync Server 2013 中安裝轉送伺服器](lync-server-2013-install-the-files-for-mediation-server.md)的檔案中的程式，在集區中的每個轉送伺服器上安裝檔案。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

