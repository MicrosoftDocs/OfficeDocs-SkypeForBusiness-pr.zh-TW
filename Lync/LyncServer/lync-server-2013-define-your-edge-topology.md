---
title: Lync Server 2013：定義您的 edge 拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceba1f397493ac0ef6961099877643f802c11d93
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504560"
---
# <a name="define-your-edge-topology-in-lync-server-2013"></a>在 Lync Server 2013 中定義您的 edge 拓撲

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

您必須使用拓撲產生器來建立拓撲，而且必須先設定至少一個內部前端集區或 Standard Edition server，才能部署 Edge Server。 使用下列程式可定義單一 Edge Server 的 edge 拓撲，然後使用在 [Lync server 2013 中發佈拓撲中](lync-server-2013-publish-your-topology.md) 的程式，並 [將 lync server 2013 拓撲複製到外部媒體以進行 edge 安裝](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) ，以發行拓撲，並使其可供 edge Server 使用。

<div>


> [!NOTE]  
> 內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。



</div>

若要在新增或移除伺服器角色時，成功發行、啟用或停用拓撲，您必須以 RTCUniversalServerAdmins 和 Domain Admins 群組成員的使用者身分登入。 您也可以授與當伺服器角色新增至使用者帳戶時所需的管理員權限。 如需詳細資訊，請參閱 Standard Edition server 或 Enterprise Edition server 部署檔中的 [Lync server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md) 。 若要進行其他組態變更，則僅需要 RTCUniversalServerAdmins 群組的成員資格。

如果您已在定義及發行內部拓撲時定義 Edge 拓撲，而且不需要對先前所定義的 Edge 拓撲進行變更，則不需要再定義和發行它一次。 只有需要對 Edge 拓撲進行變更時，才要使用下列程序。 您必須讓先前定義及發佈的拓撲可供 Edge Server 使用，您可以使用 [匯出 Lync Server 2013 拓撲中的程式，並將它複製到 edge 安裝的外部媒體](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)。

<div>


> [!IMPORTANT]  
> 您無法從 Edge Server 執行拓撲產生器。 您必須從前端伺服器或 Standard Edition Server 加以執行。



</div>

定義 Edge Server 拓撲的程式是在拓撲產生器中完成。 以下列出三個您可用來規劃和設定的主要 Edge Server 拓撲類型：

  - 定義單一 Edge Server 的拓撲

  - 定義負載平衡 Edge Server 集區的拓撲

  - 定義硬體負載平衡 Edge 集區的拓撲

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a>若要定義單一 Edge Server 的拓撲

1.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  在主控台樹狀目錄中，展開想要部署 Edge Server 的網站。

3.  以滑鼠右鍵按一下 [ **Edge**集區]，然後按一下 [ **新增 edge 集**區]。

4.  在 **[定義新的 Edge 集區]** 中，按 **[下一步]**。

5.  在 **[定義 Edge 集區 FQDN]** 中，執行下列動作：
    
      - 在 **[集區 FQDN]** 中，輸入 Edge Server 適用的內部介面的完整網域名稱 (FQDN)。
        
        <div>
        

        > [!IMPORTANT]  
        > 您指定的名稱必須與伺服器上設定的電腦名稱一模一樣。 根據預設，未加入網域的電腦，其電腦名稱是簡稱，而不是 FQDN。 拓撲產生器使用 Fqdn，而非短名稱。 因此，在要部署為 Edge Server 的電腦 (未加入網域) 名稱中，您必須設定 DNS 尾碼。 當您為 Lync Server、Edge Server 及集區指派 FQDN 時，只能使用標準字元 (包括 A–Z、a–z、0–9 與連字號)。 請勿使用 Unicode 字元或底線。 當 FQDN 必須指派給憑證的 SN 時，外部 DNS 與公用 CA 通常不支援在 FQDN 中使用非標準字元。 如需將 DNS 尾碼新增至電腦名稱稱的詳細資訊，請參閱 <A href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中設定 edge 支援的 dns</A>。

        
        </div>
    
      - 按一下 **[單一電腦集區]**，然後按 **[下一步]**。

6.  在 **[選取功能]** 中，執行下列動作：
    
      - 如果您打算針對 SIP 存取服務、Lync Server 2013 Web 會議服務，以及 A/V Edge service 使用單一 FQDN 和 IP 位址，請選取 [ **使用單一 fqdn 和 Ip 位址** ] 核取方塊。
    
      - 如果您打算啟用同盟，請選取 [啟用此 Edge 集區的同盟 (連接埠 5061)]**** 核取方塊。
        
        <div>
        

        > [!NOTE]  
        > 您可以選取此選項，但是只能將組織中的一個 Edge 集區或 Edge Server 發行到外部，以進行同盟。所有由同盟使用者 (包括公用立即訊息 (IM) 使用者) 進行的存取都會通過相同的 Edge 集區或單一 Edge Server。例如，如果您的部署範圍包括分別部署在紐約與倫敦的一個 Edge 集區或單一 Edge Server，而您針對紐約的 Edge 集區或單一 Edge Server 啟用了同盟支援，則同盟使用者的訊號流量會通過紐約的 Edge 集區或單一 Edge Server。儘管位於倫敦的內部使用者在致電倫敦的同盟使用者時，使用了倫敦集區或 Edge Server 以傳送音訊/視訊流量，與倫敦的使用者進行通訊時也適用這種情況。

        
        </div>
    
      - 如果您打算針對部署支援 Extensible Messaging and Presence Protocol (XMPP)，請選取 [啟用 XMPP 同盟 (連接埠 5269)]**** 核取方塊

7.  在 [選取 IP 選項]**** 中，執行下列動作：
    
      - **在內部介面上啟用 IPv4**：若要將 IPv4 位址套用至 edge Server 或 edge 集區內部介面，請選取此核取方塊。
    
      - **在內部介面上啟用 IPv6**：若要將 IPv6 位址套用至 edge Server 或 edge 集區內部介面，請選取此核取方塊。
    
      - **在外部介面上啟用 IPv4**：若要將 IPv4 位址套用至 edge Server 或 edge 集區外部介面，請選取此核取方塊。
    
      - **在外部介面上啟用 IPv6**：若要將 IPv6 位址套用至 edge Server 或 edge 集區外部介面，請選取此核取方塊。
    
    您也可以將 Edge Server 或 Edge 集區設定為使用網路位址轉譯位址的外部 IP 位址。 您可以藉由選取 [此 Edge 集區的外部 IP 位址由 NAT 轉譯]**** 核取方塊，來執行此動作。

8.  在 **[外部 FQDN]** 中，執行下列動作：
    
      - 如果您在 **[選取功能]** 中已選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 **[SIP 存取]** 中輸入外部 FQDN。
        
        <div>
        

        > [!NOTE]  
        > 如果您選擇此選項，則必須為每個 Edge Service 分別指定不同的連接埠號碼 (建議的連接埠設定：Access Edge Service 為 5061、Web Conferencing Edge Service 為 444，A/V Edge Service 為 443)。選取此選項，不僅有助於防止潛在的連線問題，也可以簡化組態，原因是之後您就可以針對這三個服務使用相同的連接埠號碼 (例如，443)。

        
        </div>
    
      - 如果您在 **[選取功能]** 中未選擇使用單一 FQDN 和 IP 位址，請輸入 **[SIP 存取]**、**[Web 會議]** 和 **[音訊/視訊]** 的外部 FQDN，並保留預設連接埠。

9.  按 **[下一步]**。

10. 在 [定義內部 IP 位址]**** 中，視需要在 [內部 IPv4 位址]**** 和 [內部 IPv6 位址]****  中鍵入 Edge Server 的 IP 位址。按 [下一步]****。

11. 在 **[定義外部 IP 位址]** 中，執行下列動作：
    
      - 如果您選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 [SIP 存取]**** 中鍵入 Edge Server 的外部 IPv4 位址，然後按 [下一步]****。
    
      - 如果您選擇使用 IPv6 位址，請在 [SIP 存取]**** 中鍵入 Edge Server 的外部 IPv6 位址，然後按 [下一步]****
    
      - 如果您未選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 [SIP 存取]****、[Web 會議]**** 和 [A/V 會議]**** 中鍵入 Edge Server 的外部 IPv4 位址，然後按 [下一步]****。
    
      - 如果您選擇使用 IPv6 位址且未選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 [SIP 存取]****、[Web 會議]**** 和 [A/V 會議]**** 中鍵入 Edge Server 的外部 IPv6 位址，然後按 [下一步]****。
        
        <div>
        

        > [!NOTE]  
        > 如果您未選擇啟用和指派 IPv6 位址，將不會看見此對話方塊。

        
        </div>

12. 如果您選擇使用 NAT，則會出現一個對話方塊。在 [A/V Edge Service 的公用 IPv4 位址]**** 中，鍵入要由 NAT 轉譯的公用 IPv4 位址，然後按 [下一步]****。
    
    <div>
    

    > [!NOTE]  
    > 這應該是 A/V Edge Service 的外部 IP 位址。

    
    </div>

13. 如果您選擇使用 NAT 和 IPv6 位址，則會出現一個對話方塊。在 [A/V Edge Service 的公用 IPv6 位址]**** 中，鍵入要由 NAT 轉譯的公用 IPv6 位址，然後按 [下一步]****。
    
    <div>
    

    > [!NOTE]  
    > 這應該是 A/V Edge Service 的外部 IP 位址。

    
    </div>

14. 在 [定義下一個躍點]**** 的 [下一個躍點集區]**** 中，選取內部集區 (可以是前端集區或 Standard Edition 集區) 的名稱。或者，如果您的部署包括 Director，請選取 Director。然後按 [下一步]****。

15. 在 **[建立前端集區的關聯]** 中，指定一個或多個要與此 Edge Server 相關聯的內部集區 (可包括前端集區及 Standard Edition 伺服器)，方法是選取要使用此 Edge Server 與所支援外部使用者進行通訊的內部集區的名稱。
    
    <div>
    

    > [!NOTE]  
    > 針對 A/V 流量，每個內部集區都只能與一個負載平衡 Edge 集區或單一 Edge Server 相關聯。如果您已有與 Edge 集區或 Edge Server 相關聯的內部集區，則會出現警告，指出內部集區已與 Edge 集區或 Edge Server 相關聯。如果您選取已經與其他 Edge Server 相關聯的集區，將會使關聯產生變更。

    
    </div>

16. 按一下 **[完成]**。

17. 發行您的拓撲。

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>為 DNS 負載平衡 Edge Server 集區定義拓撲

1.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  在主控台樹狀目錄中，展開想要部署 Edge Server 的網站。

3.  以滑鼠右鍵按一下 [Edge 集區]****，然後按一下 [新增 Edge 集區]****。

4.  在 [定義新的 Edge 集區]**** 中，按 [下一步]****。

5.  在 [定義 Edge 集區 FQDN]**** 中，執行下列動作：
    
      - 在 [集區 FQDN]**** 中，鍵入適用於 Edge 集區之內部連線的完整網域名稱 (FQDN)。
        
        <div>
        

        > [!IMPORTANT]  
        > 您為集區指定的名稱必須是內部 Edge 集區名稱。 此名稱必須定義為 FQDN。 拓撲產生器使用 Fqdn，而非短名稱。 當您為 Lync Server、Edge Server 以及集區指派 FQDN 時，只能使用標準字元 (包括 A–Z、a–z、0–9 與連字號)。 請勿使用 Unicode 字元或底線。 當必須將 FQDN 指派給憑證的 SN 時，外部 DNS 與公用 CA 通常不支援在 FQDN 中使用非標準字元。

        
        </div>
    
      - 按一下 [多部電腦集區]****，然後按 [下一步]****。

6.  在 [選取功能]**** 中，執行下列動作：
    
      - 如果您打算針對 SIP 存取、Lync Server 2013 Web 會議服務和 A/V Edge service 使用單一 FQDN 和 IP 位址，請選取 [ **使用單一 fqdn 和 Ip 位址** ] 核取方塊。
    
      - 如果您打算啟用同盟，請選取 [啟用此 Edge 集區的同盟 (連接埠 5061)]**** 核取方塊。按 [下一步]****。
        
        <div>
        

        > [!NOTE]  
        > 您可以選取此選項，但是只能將組織中的一個 Edge 集區或一部 Edge Server 發行到外部，以進行同盟。所有由同盟使用者 (包括公用立即訊息 (IM) 使用者) 進行的存取都會通過相同的 Edge 集區或單一 Edge Server。例如，如果您的部署包括了分別部署在紐約與倫敦的一個 Edge 集區或單一 Edge Server，而您針對紐約的 Edge 集區或單一 Edge Server 啟用了同盟支援，則同盟使用者的訊號流量會通過紐約的 Edge 集區或單一 Edge Server。儘管位於倫敦的內部使用者在致電倫敦的同盟使用者時，使用了倫敦集區或 Edge Server 來傳送 A/V 流量，與倫敦的使用者進行通訊時也適用這種情況。

        
        </div>
    
      - 如果您打算針對部署支援 Extensible Messaging and Presence Protocol (XMPP)，請選取 [啟用 XMPP 同盟 (連接埠 5269)]**** 核取方塊

7.  按 [下一步]****。

8.  在 [選取 IP 選項]**** 中，執行下列動作：
    
      - **在內部介面上啟用 IPv4**：若要將 IPv4 位址套用至 edge Server 或 edge 集區內部介面，請選取此核取方塊。
    
      - **在內部介面上啟用 IPv6**：若要將 IPv6 位址套用至 edge Server 或 edge 集區內部介面，請選取此核取方塊。
    
      - **在外部介面上啟用 IPv4**：若要將 IPv4 位址套用至 edge Server 或 edge 集區外部介面，請選取此核取方塊。
    
      - **在外部介面上啟用 IPv6**：若要將 IPv6 位址套用至 edge Server 或 edge 集區外部介面，請選取此核取方塊。
    
    您也可以將 Edge Server 或 Edge 集區設定為使用網路位址轉譯位址的外部 IP 位址。 您可以藉由選取 [此 Edge 集區的外部 IP 位址由 NAT 轉譯]**** 核取方塊，來執行此動作。

9.  在 [外部 FQDN]**** 中，執行下列動作：
    
      - 如果您在 [選取功能]**** 中選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 [SIP 存取]**** 中輸入外部 FQDN。
        
        <div>
        

        > [!NOTE]  
        > 如果您選擇此選項，則必須為每個 Edge Service 指定不同的連接埠號碼 (建議的連接埠設定：Access Edge Service 為 5061、Web Conferencing Edge Service 為 444，A/V Edge Service 為 443)。選取此選項，不僅有助於防止潛在的連線問題，也可以簡化組態，因為之後您就可針對這三個服務使用相同的連接埠號碼 (例如，443)。

        
        </div>
    
      - 如果您在 [選取功能]**** 中未選擇使用單一 FQDN 和 IP 位址，請在 [SIP 存取]**** 中，鍵入您為 Edge 集區之對外端選擇的 FQDN。在 [Web 會議]**** 中，鍵入您為此 Edge 集區伺服器之對外端選擇的 IP 位址。在 [音訊/視訊]**** 中，鍵入您為 Edge 集區之對外端選擇的 FQDN。請使用預設連接埠。

10. 按 [下一步]****。

11. 在 **[定義此集區中的電腦]** 中，按一下 **[新增]**。

12. 在 [內部 FQDN 和 IP 位址]**** 中，執行下列動作：
    
      - 在 [內部 IPv4 位址]**** 中，針對想要在此集區中建立的第一部 Edge Server 適用的需求鍵入 IPv4 位址和 [內部 IPv6 位址]****。
    
      - 在 [內部 FQDN]**** 中，鍵入想要在此集區中建立的第一部 Edge Server 的 FQDN。
        
        <div>
        

        > [!NOTE]  
        > 您指定的名稱必須與伺服器上設定的電腦名稱一模一樣。 根據預設，未加入網域的電腦，其電腦名稱是簡短名稱，而不是 FQDN。 拓撲產生器使用 Fqdn，而非短名稱。 因此，在要部署為 Edge Server 的電腦 (未加入網域) 名稱中，您必須設定 DNS 尾碼。 當您為 Lync Server、Edge Server、集區及陣列指派 FQDN 時，只能使用標準字元 (包括 A–Z、a–z、0–9 與連字號)。 請勿使用 Unicode 字元或底線。 當 FQDN 必須指派給憑證的 SN 時，外部 DNS 與公用 CA 通常不支援在 FQDN 中使用非標準字元。 如需將 DNS 尾碼新增至電腦名稱稱的詳細資訊，請參閱 <A href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中設定 edge 支援的 dns</A>。

        
        </div>

13. 按 [下一步]****。

14. 在 **[定義外部 IP 位址]** 中，執行下列動作：
    
      - 如果您選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 **[SIP 存取]** 中輸入 Edge Server 的外部 IP 位址。
    
      - 如果您未選擇針對 SIP 存取、Web 會議服務和 A/V 會議服務使用單一 FQDN 和 IP 位址，請在 [SIP 存取]**** 中鍵入您已為此 Edge 集區伺服器之對外端選擇的 IP 位址。在 [Web 會議]**** 中，鍵入您已為此 Edge 集區伺服器之對外端選擇的 IP 位址。在 [A/V 會議]**** 中，鍵入您已為此 Edge 集區伺服器之對外端選擇的 IP 位址。

15. 按 [下一步]****。

16. 如果您選擇啟用 IPv6 位址，請在 [定義外部 IP 位址]**** 中，執行下列動作：
    
      - 如果您選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 [SIP 存取]**** 中鍵入 Edge Server 的外部 IPv6 位址。
    
      - 如果您未選擇針對 SIP 存取、Web 會議服務和 A/V 會議服務使用單一 FQDN 和 IP 位址，請在 [SIP 存取]**** 中鍵入您已為此 Edge 集區伺服器之對外端選擇的 IPv6 位址。在 [Web 會議]**** 中，鍵入您已為此 Edge 集區伺服器之對外端選擇的 IPv6 位址。在 [A/V 會議]**** 中，鍵入您已為此 Edge 集區伺服器之對外端選擇的 IPv6 位址。
    
    <div>
    

    > [!NOTE]  
    > 如果您未選擇啟用和指派 IPv6 位址，將不會看見此對話方塊。

    
    </div>

17. 按一下 [完成]****。
    
    <div>
    

    > [!NOTE]  
    > 您現在可以在 [定義此集區中的電腦]<STRONG></STRONG> 對話方塊中看到剛才在集區中建立的第一部 Edge Server。

    
    </div>

18. 在 [定義此集區中的電腦]**** 中，按一下 [新增]****，然後針對想要新增至 Edge 集區的第二部 Edge Server 重複執行步驟 11 到 14。

19. 重複執行步驟 11 到 14 之後，按一下 [定義此集區中的電腦]**** 中的 [下一步]****。
    
    <div>
    

    > [!NOTE]  
    > 此時，您可以在集區中同時看到這兩部 Edge Server。

    
    </div>

20. 如果您選擇使用 NAT，則會出現一個對話方塊。在 [公用 IP 位址]**** 中，鍵入要由 NAT 轉譯的公用 IPv4 和 IPv6 (如果適當) 位址，然後按 [下一步]****。
    
    <div>
    

    > [!NOTE]  
    > 此處的 IP 位址應是 A/V Edge 的外部 IP 位址。

    
    </div>

21. 在 [定義下一個躍點]**** 的 [下一個躍點集區]**** 清單中，選取內部集區 (可以是前端集區或 Standard Edition 集區) 的名稱。或者，如果您的部署包括 Director，請選取 Director 的名稱。然後按 [下一步]****。

22. 在 **[建立前端集區的關聯]** 中，指定一個或多個要與此 Edge Server 相關聯的內部集區 (可包括前端集區及 Standard Edition 伺服器)，方法是選取要使用此 Edge Server 與所支援外部使用者進行通訊的內部集區的名稱。
    
    <div>
    

    > [!NOTE]  
    > 針對 A/V 流量，每個內部集區都只能與一個負載平衡 Edge 集區或單一 Edge Server 相關聯。如果您已有與 Edge 集區或 Edge Server 相關聯的內部集區，則會出現警告，指出內部集區已與 Edge 集區或 Edge Server 相關聯。如果您選取已經與其他 Edge Server 相關聯的集區，將會使關聯產生變更。

    
    </div>

23. 按一下 **[完成]**。

24. 發行您的拓撲。

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>定義硬體負載平衡 Edge Server 集區的拓撲

1.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  在主控台樹狀目錄中，展開想要部署 Edge Server 的網站。

3.  以滑鼠右鍵按一下 [ **Edge**集區]，然後選取 [ **新增 edge 集**區]。

4.  在 **[定義新的 Edge 集區]** 中，按 **[下一步]**。

5.  在 **[定義 Edge 集區 FQDN]** 中，執行下列動作：
    
      - 在 [FQDN]**** 中，鍵入您已為 Edge 集區之對內端選擇的完整網域名稱 (FQDN)。
        
        <div>
        

        > [!IMPORTANT]  
        > 您為集區指定的名稱必須是內部 Edge 集區名稱。 此名稱必須定義為 FQDN。 拓撲產生器使用 Fqdn，而非短名稱。 當您為 Lync Server、Edge Server 以及集區指派 FQDN 時，只能使用標準字元 (包括 A–Z、a–z、0–9 與連字號)。 請勿使用 Unicode 字元或底線。 當 FQDN 必須指派給憑證的 SN 時，外部 DNS 與公用 CA 通常不支援在 FQDN 中使用非標準字元。

        
        </div>
    
    <!-- end list -->
    
      - 按一下 [ **多部電腦集**區]，然後按一下 **[下一步]**。

6.  在 **[選取功能]** 中，執行下列動作：
    
      - 如果您打算針對 SIP 存取服務、Lync Server Web 會議服務和 A/V Edge service 使用單一 FQDN 和 IP 位址，請選取 [ **使用單一 fqdn & IP 位址** ] 核取方塊。
    
      - 如果您打算啟用同盟，請選取 **[啟用此 Edge 集區的同盟 (連接埠 5061)]** 核取方塊。
        
        <div>
        

        > [!NOTE]  
        > 您可以選取此選項，但是只能將組織中的一個 Edge 集區或一部 Edge Server 發行到外部，以進行同盟。所有由同盟使用者 (包括公用立即訊息 (IM) 使用者) 進行的存取都會通過相同的 Edge 集區或單一 Edge Server。例如，如果您的部署包括了分別部署於紐約與倫敦的一個 Edge 集區或單一 Edge Server，而您針對紐約的 Edge 集區或單一 Edge Server 啟用了同盟支援，則同盟使用者的訊號流量會通過紐約的 Edge 集區或單一 Edge Server。儘管位於倫敦的內部使用者在致電倫敦的同盟使用者時，使用了倫敦集區或 Edge Server 來傳送 A/V 流量，與倫敦的使用者進行通訊時也適用這種情況。

        
        </div>
    
      - 如果您打算針對部署支援 Extensible Messaging and Presence Protocol (XMPP)，請選取 [啟用 XMPP 同盟 (連接埠 5269)]**** 核取方塊

7.  按 [下一步]****。

8.  在 [選取 IP 選項]**** 中，執行下列動作：
    
      - **在內部介面上啟用 IPv4**：若要將 IPv4 位址套用至 edge Server 或 edge 集區內部介面，請選取此核取方塊。
    
      - **在內部介面上啟用 IPv6**：若要將 IPv6 位址套用至 edge Server 或 edge 集區內部介面，請選取此核取方塊。
    
      - **在外部介面上啟用 IPv4**：若要將 IPv4 位址套用至 edge Server 或 edge 集區外部介面，請選取此核取方塊。
    
      - **在外部介面上啟用 IPv6**：若要將 IPv6 位址套用至 edge Server 或 edge 集區外部介面，請選取此核取方塊。
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>「請不要」</STRONG>選取 [由 NAT 轉譯此 Edge 集區的外部 IP 位址]<STRONG></STRONG> 核取方塊。當您使用硬體負載平衡時，不支援網路位址轉譯 (NAT)。

    
    </div>

9.  在 [外部 FQDN]**** 中，執行下列動作：
    
      - 如果您在 [選取功能]**** 中選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 [SIP 存取]**** 中鍵入外部 FQDN。
        
        <div>
        

        > [!NOTE]  
        > 如果您選取此選項，則必須為每個 Edge Service 分別指定不同的連接埠號碼 (建議的連接埠設定：Access Edge Service 為 5061、Web Conferencing Edge Service 為 444，A/V Edge Service 為 443)。選取此選項，不僅有助於防止潛在的連線問題，也可以簡化組態，因為之後您就可以針對這三個服務使用相同的連接埠號碼 (例如，443)。

        
        </div>
    
      - 如果您在 [選取功能]**** 中未選擇使用單一 FQDN 和 IP 位址，請在 [SIP 存取]**** 中，鍵入您為 Edge 集區之對外端選擇的 FQDN。在 [Web 會議]**** 中，鍵入您為 Edge 集區之對外端選擇的 FQDN。在 [音訊/視訊]**** 中，鍵入您為 Edge 集區之對外端選擇的 FQDN。請使用預設連接埠。
        
        <div>
        

        > [!NOTE]  
        > 這些會是集區的對外虛擬 IP (VIP) FQDN。

        
        </div>

10. 按 [下一步]****。

11. 在 [定義此集區中的電腦]**** 中，按一下 [新增]****。

12. 在 [定義外部 IP 位址]**** 中，執行下列動作：
    
      - 如果您選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 [SIP 存取]**** 中鍵入 Edge Server 的外部 IPv4 位址，並在 [SIP 存取]**** 中鍵入 Edge Server 的外部 IP 位址。
    
      - 如果您未選擇針對 SIP 存取、Web 會議服務和 A/V 會議服務使用單一 FQDN 和 IP 位址，請在 [SIP 存取]**** 中鍵入您已為此 Edge 集區伺服器之對外端選擇的 IP 位址。在 [Web 會議]**** 中，鍵入您為此 Edge 集區伺服器之對外端選擇的 IP 位址。在 [A/V 會議]**** 中，鍵入您已為此 Edge 集區伺服器之對外端選擇的 IP 位址。

13. 按 [下一步]****。

14. 如果您選擇啟用 IPv6 位址，請在 [定義外部 IP 位址]**** 中，執行下列動作：
    
      - 如果您選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 [SIP 存取]**** 中鍵入 Edge Server 的外部 IPv6 位址。
    
      - 如果您未選擇針對 SIP 存取、Web 會議服務和 A/V 會議服務使用單一 FQDN 和 IP 位址，請在 [SIP 存取]**** 中鍵入您已為此 Edge 集區伺服器之對外端選擇的 IPv6 位址。在 [Web 會議]**** 中，鍵入您已為此 Edge 集區伺服器之對外端選擇的 IPv6 位址。在 [A/V 會議]**** 中，鍵入您已為此 Edge 集區伺服器之對外端選擇的 IPv6 位址。
    
    <div>
    

    > [!NOTE]  
    > 如果您未選擇啟用和指派 IPv6 位址，將不會看見此對話方塊。

    
    </div>

15. 按一下 [完成]****。
    
    <div>
    

    > [!NOTE]  
    > 您現在可以在 <STRONG>[定義此集區中的電腦]</STRONG> 對話方塊中看到剛才在集區中建立的第一個 Edge Server。

    
    </div>

16. 在 [定義此集區中的電腦]**** 中，按一下 [新增]****，然後針對想要新增至 Edge 集區的第二個 Edge Server 重複步驟 11 到 14。

17. 重複步驟 11 到 14 之後，按一下 **[定義此集區中的電腦]** 中的 **[下一步]**。
    
    <div>
    

    > [!NOTE]  
    > 此時，您可以在集區中同時看到這兩個 Edge Server。

    
    </div>

18. 在 **[定義下一個躍點]** 的 **[下一個躍點集區]** 清單中，選取內部集區 (可以是前端集區或 Standard Edition 集區) 的名稱。或者，如果您的部署包括 Director，請選取 Director 的名稱。然後按 **[下一步]**。

19. 在 **[建立前端集區的關聯]** 中，指定一個或多個要與此 Edge Server 相關聯的內部集區 (可包括前端集區及 Standard Edition 伺服器)，方法是選取要使用此 Edge Server 與所支援外部使用者進行通訊的內部集區的名稱。
    
    <div>
    

    > [!NOTE]  
    > 針對 A/V 流量，每個內部集區都只能與一個負載平衡 Edge 集區或單一 Edge Server 相關聯。如果您已有與 Edge 集區或 Edge Server 相關聯的內部集區，則會出現警告，指出內部集區已與 Edge 集區或 Edge Server 相關聯。如果您選取已經與其他 Edge Server 相關聯的集區，將會使關聯產生變更。

    
    </div>

20. 按一下 **[完成]**。

21. 發行您的拓撲。

</div>

</div>

<span> </span>

</div>

</div>

</div>

