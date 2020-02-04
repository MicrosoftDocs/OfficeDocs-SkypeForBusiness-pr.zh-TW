---
title: 定義和設定前端集區或 Standard Edition Server
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
ms.openlocfilehash: ddc430370c59e279e0e36aa662da0f33973e0d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a>在 Lync Server 2013 中定義和設定前端集區或 Standard Edition Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-08_

此程式不需要本機系統管理員或許可權網域群組的成員資格。 您應該以標準使用者的身分登入電腦。

如果您要部署企業伺服器，則池中的最小前端伺服器數必須在任何時間執行。 下表摘要說明這些需求。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>池中的前端伺服器總數</th>
<th>必須執行才能供擁有池中運作的伺服器數量</th>
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
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>7-8</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>9-10</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>11-12</p></td>
<td><p>6</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> 在 Lync Server 2013 中，您可以隨時從池中新增或移除前端伺服器，您必須重新開機服務。 移除及新增伺服器應做為個別的作業。 例如，如果您要新增兩個前端伺服器並移除兩個前端伺服器，請使用下列程式： 
> <OL>
> <LI>
> <P>移除兩個前端伺服器。</P>
> <LI>
> <P>發佈並重新啟用拓撲。</P>
> <LI>
> <P>重新開機服務</P>
> <LI>
> <P>新增兩個前端伺服器。</P>
> <LI>
> <P>發佈並重新啟用拓撲。</P>
> <LI>
> <P>重新開機服務。</P></LI></OL>



</div>

定義拓朴之後，請使用下列程式為您的網站定義前端池。 如需定義拓朴的詳細資料，請參閱[在 Lync Server 2013 的拓撲產生器中定義及設定拓撲](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)。

<div>

## <a name="to-define-a-front-end-pool"></a>定義前端池

1.  在 [定義新的前臺端池] 嚮導的 [**定義新的前端池**] 頁面上，按一下 **[下一步]**。

2.  在 [**定義前端端池 FQDN** ] 頁面上，輸入您要建立之池的完整功能變數名稱（FQDN），按一下 [**企業版頂層端池**]，然後按一下 **[下一步]**。

3.  在 [**定義此池中的電腦**] 頁面上，輸入池中第一個前端伺服器的電腦 FQDN，然後按一下 [**新增**]。 針對您想要新增至池中的任何其他電腦（最多十二個）重複此步驟，然後按 **[下一步]**。

4.  在 [**選取功能**] 頁面上，選取您要用於此前端池之功能的核取方塊。 例如，如果您只部署立即訊息（IM）與目前狀態的功能，您可以選取 [**會議**] 核取方塊來允許多方 IM，但不會選取 [**撥入（PSTN）會議**]、[**企業語音**] 或 [**通話許可控制**] 核取方塊，因為它們代表語音、影片和共同作業會議功能。
    
      - **會議**   此選項可啟用一組豐富的功能，包括：
        
          - Im 會話中有超過兩個雙方的 IM。
        
          - 會議，包括檔共同作業、應用程式共用和桌面共用。
        
          - A/V 會議，可讓使用者擁有即時音訊/視頻（A/V）會議，而不需要外部服務（例如 Live Meeting 服務或協力廠商音訊橋接器）。
    
      - **使用 [撥入（PSTN）會議**   ]，使用者可以在不需要音訊會議提供者的情況下，使用公開交換的電話網絡（pstn）電話來加入 Lync Server 2013 會議的音訊部分。
    
      - **企業語音**   企業語音是 Lync Server 2013 的語音語音（VoIP）方案，可讓使用者撥打及接聽電話。 如果您打算使用 Lync Server 2013 進行語音通話、語音信箱，以及使用硬體裝置或軟體用戶端的其他功能，就可以部署此功能。
    
      - **呼叫許可控制（CAC）**   CAC 會根據可用的網路頻寬判斷是否允許建立即時通訊會話，例如語音或視頻通話。 如果您只部署 IM 和目前狀態，則不需要 CAC，因為這兩個功能都不會使用 CAC。
    
      - ****[封存封存] 提供一種方式，讓您能夠透過 Lync Server 2013 來封存 IM 內容、會議（會議）內容，或同時傳送這兩者。   
    
      - **[監視**   監視伺服器] 可讓您收集數位資料來描述您的網路和端點的媒體質量、與 VoIP 通話相關的使用資訊、IM 訊息、A/V 交談、會議、應用程式共用及檔案傳輸，以及呼叫錯誤與失敗呼叫的疑難排解資訊。
    
    <div>
    

    > [!NOTE]
    > 如果您想要在您的部署中啟用 CAC，必須在每個中央網站只啟用一個池中的 CAC。 如果您要部署語音功能或 A/V 會議，建議使用 CAC。

    
    </div>
    
    下表顯示可用的功能（top），以及提供給使用者的功能（左圖）。 表格中的選取範圍是您應該選取哪些專案，才能為您的組織啟用這些功能。
    
    
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
    <th>企業語音</th>
    <th>通話許可控制</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>立即訊息與顯示狀態</p></td>
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
    <td><p>企業語音</p></td>
    <td></td>
    <td></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    </tr>
    </tbody>
    </table>


5.  在 [**選取 collocated 伺服器角色**] 頁面上，您可以 Collocate 前端伺服器上的中繼伺服器，或將它部署為獨立伺服器。
    
    您可以 collocate 前端池的中繼伺服器。
    
      - 如果您想要在企業版前端池中 collocate 轉送伺服器，請確認已選取此核取方塊。 伺服器角色將會部署在池伺服器上。
    
      - 如果您想要將中繼伺服器部署為獨立伺服器，請清除適當的核取方塊。 在您完全部署前端伺服器之後，您將會在個別的部署步驟中部署轉送伺服器。
    
    <div>
    

    > [!NOTE]
    > 我們建議您盡可能 collocate 中繼伺服器。 如需 collocated 或獨立中繼伺服器支援的詳細資料，請參閱規劃檔中的<A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Lync server 2013 中的中繼伺服器元件與拓撲</A>。

    
    </div>

6.  [**關聯伺服器角色與此前端池**] 頁面可讓您定義伺服器角色，並將其與前端池建立關聯。 下列角色可供使用：
    
    **啟用邊緣池**   定義並關聯單一邊緣伺服器或邊緣伺服器池。 Edge 伺服器可協助組織內部使用者與組織外部人員之間的通訊與共同作業，包括聯盟使用者。
    
    您可以使用兩種可能的案例來部署及關聯伺服器角色：
    
    針對案例1，您正在定義新安裝的新拓撲。 您可以採用下列兩種方式的其中一個方法來進行安裝：
    
      - 讓核取方塊保持不動，然後繼續定義拓撲。 在您已發佈、設定及測試前端與後端伺服器角色之後，您可以再次執行拓撲建立程式，以將角色服務器新增到拓撲結構中。 此策略可讓您測試前端池和執行 SQL Server 的伺服器，而不需要額外的角色進一步複雜。 完成初始測試之後，您可以再次執行拓撲建立器，以選取您需要部署的角色。
    
      - 選取您要安裝的角色，然後設定硬體以適應選取的角色。
    
    若是案例二，您已有部署，且您的基礎結構已準備好使用新角色，或者您需要將現有角色與新的前端伺服器建立關聯：
    
      - 在這種情況下，您將會選取您想要部署或與新的前端伺服器建立關聯的角色。 不論是哪一種情況，您都會繼續定義角色、設定任何所需的硬體，以及繼續安裝。

7.  在 [**定義 SQL store** ] 頁面上，執行下列其中一項操作：
    
      - 若要使用已在拓撲中定義的現有 SQL Server store，請選取 **[SQL store**] 中的實例。
    
      - 若要定義新的 SQL Server 實例來儲存 [池資訊]，請按一下 [**新增**]，然後在 [**定義新的 sql store** ] 對話方塊中指定**SQL Server FQDN**。
    
      - 若要指定 SQL Server 實例的名稱，請選取 [**命名實例**]，然後指定實例的名稱。
    
      - 若要使用預設實例，請按一下 [**預設實例**]。
    
      - 若要使用 SQL 鏡像，請選取 **[啟用 sql 鏡像**]，然後選取現有的實例或建立新的實例。

8.  在 [**定義檔案共用**] 頁面上，執行下列其中一項操作：
    
      - 若要使用已在您的拓撲中定義的檔案共用，請選取 [**使用先前定義**的檔案共用]。
    
      - 若要定義新的檔案共用，請選取 [**定義新的檔案共用**]，在 [檔案**伺服器 FQDN** ] 方塊中，輸入檔案共用所在之現有檔案伺服器的 FQDN，然後在 [檔案**共用**] 方塊中輸入檔案共用的名稱。
    
    <div>
    

    > [!IMPORTANT]
    > Lync Server 2013 的檔案共用無法位於前端伺服器。 請注意，在這個範例中，檔案共用已位於 SQL Server 的後端伺服器上。 這可能不是貴組織需求的最佳位置，而是檔案伺服器可能是較佳的選擇。 您可以定義檔案共用，但不需要建立檔案共用。 您必須先在您定義的位置中建立檔案共用，然後才能發佈拓撲。

    
    </div>

9.  在 [**指定 Web 服務 URL** ] 頁面上，執行下列其中一項或兩項操作：
    
    <div>
    

    > [!IMPORTANT]
    > 基底 URL 是 URL 的 Web 服務身分識別，而不是 HTTPs://。 例如，如果該池的 Web 服務的完整 URL 是https://pool01.contoso.net，則基底 url 是 pool01.contoso.net。

    
    </div>
    
    <div>
    

    > [!WARNING]
    > 如果您有多個前端池或前端伺服器，則外部 Web 服務 FQDN 必須是唯一的。 例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為<STRONG>pool01.contoso.com</STRONG>，則無法將<STRONG>pool01.contoso.com</STRONG>用於另一個前端池或前端伺服器。

    
    </div>
    
    1.  如果您要設定 DNS 負載平衡，請選取 [覆**寫內部 Web 服務池 FQDN** ] 核取方塊，輸入內部基底 url （其必須與 [池 fqdn] 不同，例如，在**內部基 url**中則\>可以是內部\<基礎 url）。
        
        <div>
        

        > [!WARNING]
        > 如果您決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 都必須是與任何其他的前端池、控制器或主管池都是唯一的。 在定義 Url 或完整功能變數名稱時，<STRONG>只使用標準字元</STRONG>（包括 a-z、A 至 z、0–9和連字號）。 請勿使用 Unicode 字元或底線。 外部 DNS 和公用 Ca 通常不支援 URL 或 FQDN 中的非標準字元（也就是，當 URL 或 FQDN 必須指派給憑證中的消費者名稱或消費者替換名稱時）。

        
        </div>
    
    2.  您也可以選擇在**外部基底 url**中輸入外部基底 url。 您可以輸入外部基底 URL，讓它有別于您的內部網域命名。 例如，您的內部網域是 contoso.net，但是您的外部功能變數名稱是 contoso.com。 您可以使用 contoso.com 功能變數名稱定義 URL。 在反向 proxy 的情況下，這也很重要。 外部基底 URL 功能變數名稱會與反向 proxy 的 FQDN 功能變數名稱相同。 立即訊息和目前狀態會要求對前端池進行 HTTP 存取。
    
    <div>
    

    > [!NOTE]
    > 若要使用 DNS 負載平衡，您必須建立適當的 DNS 記錄。 如需詳細資訊，請參閱<A href="lync-server-2013-configure-dns-for-load-balancing.md">在 Lync Server 2013 中設定負載平衡的 DNS</A>。

    
    </div>

10. 如果您在 [**選取功能**] 頁面上選取 [**會議**]，請在 [**選取 office web apps 伺服器**] 頁面上選取 [**與 office web** Apps 伺服器關聯]，然後按一下 [**新增**] （或從下拉式清單中選取現有的 Office Web apps 伺服器）。

11. 在 [**定義新的 Office Web Apps 伺服器**] 對話方塊的 [ **Office WEB apps server FQDN** ] 方塊中，輸入您 office web apps server 電腦的完整功能變數名稱（FQDN）;當您這樣做時，您的 Office Web Apps 伺服器探索 URL 應該會自動輸入至 [ **Office Web Apps server 探索 url** ] 方塊中。
    
    如果 Office Web Apps 伺服器安裝于內部部署，且位於與 Lync Server 2013 相同的網路區域中，則不應選取 [ **Office Web Apps 伺服器] 部署在外部網路（也就是 [週邊/網際網路]）** 。
    
    如果 Office Web Apps 伺服器是在您的內部防火牆外部署，請選取 [ **Office Web Apps 伺服器] 部署在外部網路（也就是 [週邊/網際網路]）**。
    
    <div>
    

    > [!NOTE]
    > 如需詳細資訊，請參閱設定<A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">與 Office Web Apps server 和 Lync server 2013 的整合</A>。

    
    </div>

12. 在 [**定義存檔 SQL store** ] 頁面上，選取現有的實例或 SQL Server，或定義新的實例來儲存與封存資料相關的資料。

13. 在 [**定義監視 SQL 存放區**] 頁面上，選取現有的實例或 SQL Server，或定義新的實例來儲存與監視資料相關聯的資料。

14. 按一下 **[下一步]**。 如果您在 [**關聯伺服器角色與此前端池**] 頁面上定義其他角色服務器，則會開啟 [個別角色配置] 嚮導頁面，讓您設定伺服器角色。 如需詳細資訊，請參閱下列內容：
    
    [在 Lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)

15. 如果您沒有選取要設定和部署的其他伺服器角色，或者當您已完成其他角色服務器的設定，請按一下 **[完成]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

