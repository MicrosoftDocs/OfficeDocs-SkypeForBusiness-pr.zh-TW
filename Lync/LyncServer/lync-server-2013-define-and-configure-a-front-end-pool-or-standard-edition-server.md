---
title: 定義及設定前端集區或 Standard Edition server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfd8cc2b12032e1283c10e26d4a9fa879621233f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a>在 Lync Server 2013 中定義及設定前端集區或 Standard Edition server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-08_

此程序不需要本機系統管理員或已授權網域群組中的成員資格。您應該以標準使用者身分登入電腦。

如果您要部署企業伺服器，集區中的前端伺服器數目下限必須在任何時間執行。 下表摘要說明這些需求。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>集區中的前端伺服器總數</th>
<th>集區執行運作所需的伺服器數目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1-2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>個</p></td>
</tr>
<tr class="even">
<td><p>7-8</p></td>
<td><p>4 </p></td>
</tr>
<tr class="odd">
<td><p>9-10</p></td>
<td><p>5 </p></td>
</tr>
<tr class="even">
<td><p>11-12</p></td>
<td><p>6 </p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> 對於 Lync Server 2013，每當您在集區中新增或移除前端伺服器時，您必須重新開機服務。 移除及新增伺服器應該做為個別的作業。 例如，如果您要新增兩部前端伺服器並移除兩部前端伺服器，請使用下列程式： 
> <OL>
> <LI>
> <P>移除兩部前端伺服器。</P>
> <LI>
> <P>發佈並重新啟動拓撲。</P>
> <LI>
> <P>重新開機服務</P>
> <LI>
> <P>新增兩部前端伺服器。</P>
> <LI>
> <P>發佈並重新啟動拓撲。</P>
> <LI>
> <P>重新啟動服務。</P></LI></OL>



</div>

定義好拓撲之後，請使用下列程式定義網站的前端集區。 如需定義拓撲的詳細資訊，請參閱[在 Lync Server 2013 的拓撲產生器中定義及設定拓撲](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)。

<div>

## <a name="to-define-a-front-end-pool"></a>定義前端集區

1.  在 [定義新前端集區] 精靈的 **[定義新前端集區]** 頁面上，按 **[下一步]**。

2.  在 [**定義前端集區 FQDN** ] 頁面上，輸入您要建立之集區的完整功能變數名稱 (FQDN) ，按一下 [ **Enterprise Edition 前端集**區]，然後按 **[下一步]**。

3.  在 [**定義此集區中的電腦**] 頁面上，輸入集區中第一部前端伺服器的電腦 FQDN，然後按一下 [**新增**]。 針對您要新增至集區的十二) ，對任何其他 (電腦重複此步驟，然後按 **[下一步]**。

4.  在「選取功能」**** 頁面上，選取您希望此前端集區擁有的功能之對應核取方塊。 例如，如果您只部署立即訊息 (IM) 和目前狀態功能，您可以選取 [**會議**] 核取方塊以允許多方 IM，但不會選取**撥入 (PSTN) 會議**、 **Enterprise Voice**或**通話許可控制**核取方塊，因為它們代表語音、影片及共同作業會議功能。
    
      - **會議**    這種選取範圍可啟用一組豐富的功能，包括：
        
          - Im 會話中有兩個以上的多方的 IM。
        
          - 會議，包含檔共同作業、應用程式共用和桌面共用。
        
          - A/V 會議，可讓使用者 (A/V) 會議，而不需要使用外部服務（例如 Live Meeting 服務或協力廠商音訊橋）進行即時音訊/視頻。
    
      - **電話撥入 (PSTN) 會議**    使用公用交換電話網路 (PSTN) 電話，而不需要音訊會議提供者，允許使用者加入 Lync Server 2013 會議的音訊部分。
    
      - **Enterprise Voice**    Enterprise Voice 是 Lync Server 2013 中的 Voice over IP (VoIP) 方案，可讓使用者撥打和接聽電話。 如果您打算使用 Lync Server 2013 進行語音通話、語音信箱，以及使用硬體裝置或軟體用戶端的其他功能，則會部署此功能。
    
      - ** (CAC) **     的通話許可控制CAC 會根據可用的網路頻寬，判斷是否允許建立即時通訊會話（例如語音或視頻通話）。 如果您只有部署 IM 與顯示狀態功能，那就不需要部署 CAC，因為兩者都不會用到 CAC 功能。
    
      - **Archiving**封存    封存為您提供一種方式，可讓您封存透過 Lync Server 2013 傳送的 IM 內容、會議 (會議) 內容或兩者。
    
      - **監控**    監控伺服器可讓您收集描述網路和端點上媒體質量的數值資料、與 VoIP 通話相關的使用資訊、IM 訊息、A/V 交談、會議、應用程式共用和檔案傳輸，以及呼叫錯誤和失敗通話的疑難排解資訊。
    
    <div>
    

    > [!NOTE]
    > 如果您想要在部署中啟用 CAC，必須在每個中央網站的恰好一個集區中啟用 CAC。 如果您要部署語音功能或 A/V 會議，則建議使用 CAC。

    
    </div>
    
    下表說明可用的功能 (上方) 以及提供給使用者使用的功能 (左側)。表中的選項代表您應該為組織選取並啟用的功能。
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th>會議</th>
    <th>電話撥入式會議</th>
    <th>Enterprise Voice</th>
    <th>通話許可控制</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>立即訊息和顯示狀態</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p>會議</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p>A/V 會議</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td><p>X</p></td>
    </tr>
    <tr class="even">
    <td><p>Enterprise Voice</p></td>
    <td></td>
    <td></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    </tr>
    </tbody>
    </table>


5.  在 [**選取組合的伺服器角色**] 頁面上，您可以在前端伺服器上組合轉送伺服器，或將其部署為獨立伺服器。
    
    您可以組合前端集區上的轉送伺服器。
    
      - 如果您想要在 Enterprise Edition 前端集區上組合轉送伺服器，請確定已選取此核取方塊。 伺服器角色將會部署在集區伺服器上。
    
      - 如果您想要將轉送伺服器部署為獨立伺服器，請清除適當的核取方塊。 在您完全部署前端伺服器後，您會在個別的部署步驟中部署轉送伺服器。
    
    <div>
    

    > [!NOTE]
    > 建議您盡可能組合轉送伺服器。 如需有關組合或獨立轉送伺服器支援的詳細資訊，請參閱規劃檔中的 Lync Server 2013 中的「中繼」<A href="lync-server-2013-components-and-topologies-for-mediation-server.md">伺服器元件和拓撲</A>。

    
    </div>

6.  [**關聯伺服器角色與此前端集**區] 頁面可讓您定義伺服器角色與前端集區的關聯。 下列為可用的角色：
    
    **啟用 Edge 集**     區定義及關聯單一 Edge Server 或 Edge Server 集區。 Edge Server 會協助組織內的使用者與組織外部的人員之間的通訊和共同作業，包括同盟使用者。
    
    您可透過以下兩種案例，部署及關聯伺服器角色：
    
    在案例一當中，您可以為全新安裝定義新的拓撲。您可透過下列兩種方式之一進行安裝後續動作：
    
      - 保持核取方塊為清除，並繼續定義拓撲。 在發佈、設定及測試前端及後端伺服器角色之後，您可以再次執行拓撲產生器，將角色服務器新增至拓撲。 此策略可讓您測試前端集區和執行 SQL Server 的伺服器，而不需要其他角色的其他複雜工作。 完成初始測試之後，您可以再次執行拓撲產生器，以選取需要部署的角色。
    
      - 選取您需要安裝的角色，然後設定硬體以容納選取的角色。
    
    在案例二中，您有現有的部署，且您的基礎結構已準備好使用新角色，或您必須將現有的角色與新的前端伺服器關聯：
    
      - 在此情況下，您會選取要部署或與新前端伺服器產生關聯的角色。 不管是哪一種情況，您都需要先定義角色並設定需要的硬體後，才開始安裝。

7.  在 [**定義 SQL 存放區**] 頁面上，執行下列其中一項操作：
    
      - 若要使用拓撲中已定義的現有 SQL Server 儲存區，請從 **[sql 存放區**] 中選取實例。
    
      - 若要定義新的 SQL Server 實例以儲存集區資訊，請按一下 [**新增**]，然後在 [**定義新的 sql 存放區**] 對話方塊中指定**SQL Server FQDN**。
    
      - 若要指定 SQL Server 實例的名稱，請選取 [**命名實例**]，然後指定實例的名稱。
    
      - 若要使用預設實例，請按一下 [**預設實例**]。
    
      - 若要使用 SQL 鏡像，請選取 **[啟用 sql 鏡像**]，然後選取現有的實例或建立新的實例。

8.  在 **[定義檔案共用]** 頁面上，執行下列其中一項：
    
      - 若要使用拓撲中已經定義的檔案共用，選取 **[使用先前定義的檔案共用]**。
    
      - 若要定義新的檔案共用，請選取 [**定義新的檔案共用**]，然後在 [檔案**伺服器 FQDN** ] 方塊中，輸入檔案共用所在的現有檔案伺服器的 FQDN，然後在 [檔案**共用**] 方塊中輸入檔案共用的名稱。
    
    <div>
    

    > [!IMPORTANT]
    > Lync Server 2013 的檔案共用不能位於前端伺服器上。 請注意，在此範例中，檔案共用位於以 SQL Server 為基礎的後端伺服器上。 這個位置可能不符合貴組織的最佳需求，使用檔案伺服器可能會更適合。 您不需要先建立檔案共用，就能定義檔案共用。 在您發行拓撲之前，必須先在定義檔案共用的位置上加以建立。

    
    </div>

9.  在 [**指定 Web 服務 URL** ] 頁面上，執行下列其中一項或兩項操作：
    
    <div>
    

    > [!IMPORTANT]
    > 基底 URL 是 URL 的 Web 服務識別身分，去除 https://。 例如，如果集區的 Web 服務完整 URL 為 https://pool01.contoso.net ，則基本 url 為 pool01.contoso.net。

    
    </div>
    
    <div>
    

    > [!WARNING]
    > 如果您有一個以上的前端集區或前端伺服器，則外部 Web 服務 FQDN 必須是唯一的。 例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為<STRONG>pool01.contoso.com</STRONG>，則無法將<STRONG>pool01.contoso.com</STRONG>用於另一個前端集區或前端伺服器。

    
    </div>
    
    1.  若要設定 DNS 負載平衡，請選取 [覆**寫內部 Web 服務集區 fqdn** ] 核取方塊，並輸入內部基本 url (，其必須與集區 FQDN 不同，例如內部基礎 Url \< \>) **內部基礎 url**中。
        
        <div>
        

        > [!WARNING]
        > 如果您決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 必須與其他任何前端集區、Director 或 Director 集區是唯一的。 在定義 URLs 或完全限定功能變數名稱時，<STRONG>只能使用標準字元</STRONG> (包括 A–Z、-Z、0–9和連字號) 。 請勿使用 Unicode 字元或底線。 在 URL 或 FQDN 中，通常不支援 URL 或 FQDN 中的非標準字元，也就是當 URL 或 FQDN 必須指派給憑證) 中的主體名稱或主體替代名稱時 (。

        
        </div>
    
    2.  （選用）在 [**外部基礎 url**] 中輸入外部基底 url。 您可以輸入外部基底 URL，使其有別于您的內部網域命名。 例如，您的內部網域為 contoso.net，而外部網域名稱為 contoso.com。 這時您可以使用 contoso.com 網域名稱來定義 URL。 在反向 Proxy 的情況中，這種作法也很重要。 外部基底 URL 功能變數名稱會與反向 proxy 的 FQDN 功能變數名稱相同。 立即訊息和目前狀態確實需要存取前端集區的 HTTP。
    
    <div>
    

    > [!NOTE]
    > 若要使用 DNS 負載平衡，您必須建立適當的 DNS 記錄。 如需詳細資訊，請參閱<A href="lync-server-2013-configure-dns-for-load-balancing.md">在 Lync Server 2013 中設定 DNS 以進行負載平衡</A>。

    
    </div>

10. 如果您在 [**選取功能**] 頁面上選取 [**會議**]，請在 [**選取 office web apps server** ] 頁面上，選取 [**將集區與 office web apps server 建立關聯**]，然後按一下 [**新增** (] 或從下拉式清單中選取現有的 Office Web Apps server) 。

11. 在 **[定義新的 Office Web Apps Server]** 對話方塊的 **[Office Web Apps Server FQDN]** 方塊中，鍵入 Office Web Apps Server 電腦的完整網域名稱 (FQDN)；執行此動作時，您的 Office Web Apps Server 探索 URL 應自動輸入至 **[Office Web Apps Server 探索 URL]** 方塊。
    
    如果 Office Web Apps Server 安裝于內部部署，且與 Lync Server 2013 位於相同的網路區域中，則選項**Office Web Apps server 部署在外部網路中 (也就是說，不應該選取周邊/網際網路) ** 。
    
    如果 Office Web Apps Server 部署在內部防火牆外，則選取 **[Office Web Apps Server 部署在外部網路 (亦即周邊/網際網路]** 選項。
    
    <div>
    

    > [!NOTE]
    > 如需詳細資訊，請參閱設定<A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Office Web Apps Server 和 Lync Server 2013 的整合</A>。

    
    </div>

12. 在 [**定義封存 SQL 存放區**] 頁面上，選取現有的實例或 SQL Server，或定義新的實例以儲存與封存資料相關聯的資料。

13. 在 [**定義監控 SQL 存放區**] 頁面上，選取現有的實例或 SQL Server，或定義新的實例以儲存與監控資料相關聯的資料。

14. 按 [下一步]****。 如果您在 [**關聯伺服器角色與此前端集**區] 頁面上定義其他角色服務器，則會開啟 [不同角色設定] 頁面，讓您設定伺服器角色。 如需詳細資訊，請參閱下列各項：
    
    [在 Lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)

15. 如果您沒有選取要設定及部署的其他伺服器角色，或是當您已完成其他角色伺服器的組態時，按一下 **[完成]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

