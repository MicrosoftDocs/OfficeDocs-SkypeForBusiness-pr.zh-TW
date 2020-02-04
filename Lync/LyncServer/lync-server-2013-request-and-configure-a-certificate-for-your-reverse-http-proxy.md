---
title: 要求以及設定反向 HTTP Proxy 的憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2597bf31c9f0cc9f4316f505811426f2c9948a6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a>在 Lync Server 2013 中要求及設定反向 HTTP Proxy 的憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-14_

您必須在執行 Microsoft Forefront 威脅管理閘道2010或 IIS ARR 的伺服器上，安裝根憑證授權單位（CA）憑證，以便將伺服器憑證頒發給執行 Microsoft Lync 的內部伺服器的 CA 基礎結構Server 2013。

您也必須在您的反向 proxy 伺服器上安裝公用 web 伺服器憑證。 這個憑證的消費者替換名稱應該包含已為使用者啟用遠端存取的每一個池的已發佈外部完整功能變數名稱（Fqdn），以及將在其中使用的所有控制器或控制器池的外部 Fqdn該 Edge 基礎結構。 Subject 替換名稱也必須包含會議簡易 URL、撥入式簡易 URL，以及如果您要部署行動應用程式並規劃使用自動探索（如下表所示）的外部自動探索服務 URL。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>值</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>消費者名稱</p></td>
<td><p>池 FQDN</p></td>
<td><p>webext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>消費者替換名稱</p></td>
<td><p>池 FQDN</p></td>
<td><p>webext.contoso.com</p>



> [!IMPORTANT]
> 受領人名稱也必須存在於 subject 替換名稱中。

</td>
</tr>
<tr class="odd">
<td><p>消費者替換名稱</p></td>
<td><p>選用控制器 Web 服務（如果已部署 Director）</p></td>
<td><p>webdirext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>消費者替換名稱</p></td>
<td><p>[會議] 簡易 URL</p>



> [!NOTE]
> 所有會議的簡單 Url 都必須在 subject 替換名稱中。 每個 SIP 網域都必須至少有一個作用中會議簡單 URL。

</td>
<td><p>meet.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>消費者替換名稱</p></td>
<td><p>電話撥入式簡易 URL</p></td>
<td><p>dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>消費者替換名稱</p></td>
<td><p>Office Web Apps 伺服器</p></td>
<td><p>officewebapps01.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>消費者替換名稱</p></td>
<td><p>外部自動探索服務 URL</p></td>
<td><p>lyncdiscover.contoso.com</p>



> [!NOTE]
> 如果您也是使用 Microsoft Exchange Server，您也需要針對 Exchange 自動探索和 web 服務 Url 設定反向 proxy 規則。

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> 如果您的內部部署是由多個標準版 server 或 [前端] 池組成，您必須針對每個外部網站伺服器陣列 FQDN 設定 web 發佈規則，或者您必須取得證書與 web 攔截器，或者您必須取得憑證其 subject 替換名稱包含所有池所使用的名稱，請將它指派給網頁監聽程式，並在多個 web 發佈規則之間共用。



</div>

<div>

## <a name="create-a-certificate-request"></a>建立憑證要求

您在反向 proxy 上建立證書申請。 您在另一部電腦上建立要求，但是您必須先將簽署的憑證匯出為私密金鑰，然後再匯入到反向 proxy 之後，再從公用憑證授權單位收到。

<div>


> [!NOTE]
> 證書申請或憑證簽署要求（CSR）是對受信任的公用憑證授權單位（CA）的要求，以驗證並簽署要求電腦的公開金鑰。 當產生證書時，就會建立一個公開金鑰和一個私用的金鑰。 只有公開金鑰是共用和簽署的。 顧名思義，公開金鑰是提供給任何公開的要求。 公開金鑰供用戶端、伺服器和其他需要安全地交換資訊並驗證電腦身分識別的申請者使用。 私人金鑰會保持安全，而且只會由建立金鑰組的電腦使用，以解密以其公開金鑰加密的郵件。 您可以使用私密金鑰來進行其他用途。 針對反向 proxy 目的，資料解碼是主要用途。 Secondarily，證書金鑰層級的憑證驗證是另一個用途，而且只限于驗證者擁有電腦的公開金鑰，或您擁有公開金鑰的電腦實際上是它所聲稱的電腦。



</div>

<div>


> [!TIP]
> 如果您同時規劃 Edge 伺服器憑證和您的反向 proxy 憑證，您應該注意到兩個憑證需求之間有很大的相似性。 當您設定並要求 Edge 伺服器憑證時，請結合邊緣伺服器與反向 proxy 消費者的替換名稱。 如果您匯出憑證和私密金鑰，然後將匯出的檔案複製到反向 proxy，然後匯入憑證/金鑰組，並視未來程式所需加以指派，就可以針對您的反向 proxy 使用相同的憑證。 請參閱 lync&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">server 2013 中 edge 伺服器方案</A>的邊緣伺服器方案的憑證需求，以及 [反向 proxy<A href="lync-server-2013-certificate-summary-reverse-proxy.md">憑證摘要-lync server 2013 中的反向</A>proxy]。 請確定您是使用可匯出的私密金鑰建立證書。 建立擁有可匯出私密金鑰的憑證和憑證要求，以供外邊緣伺服器使用時，這是一個正常做法，而在 Edge 伺服器的 Lync Server 部署嚮導中的 [憑證] 嚮導則可讓您設定 [<STRONG>製作私密金鑰可匯出</STRONG>] 標記。 當您從公用憑證授權單位收到證書要求之後，您將會匯出憑證和私密金鑰。 如需如何使用私密金鑰建立及匯出您的憑證的詳細資訊，請參閱主題為<A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Lync Server 2013 的外部邊緣介面設定</A>憑證中的「匯出證書，並在池中取得邊緣伺服器的私密金鑰」一節。 憑證的副檔名應為<STRONG>.pfx</STRONG>。



</div>

若要在指派證書及私密金鑰的電腦上產生證書簽署要求，請執行下列動作：

**建立憑證簽署要求**

1.  開啟 Microsoft 管理主控台（MMC）並新增 [憑證] 管理單元，然後選取 [**電腦**]，然後展開 [**個人**]。 如需如何在 Microsoft 管理主控台（MMC）中建立憑證主控台的詳細資料，請[http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616)參閱。

2.  以滑鼠右鍵按一下 [**憑證**]，按一下 [**所有**工作]，按一下 [**高級作業**]，按一下 [**建立自訂要求**]

3.  在 [**憑證註冊**] 頁面上，按一下 **[下一步]**。

4.  在 [**選取憑證註冊原則**] 頁面的 [**自訂要求**] 底下，選取 [**不含註冊原則，繼續**]。 按一下 **[下一步]**。

5.  在 [**自訂要求**] 頁面上，針對**範本**選取 **[（無範本）舊版金鑰**]。 除非您的憑證提供者有其他指示，否則請不要選取 [**取消選取預設擴充**]，以及在**PKCS \#10**上選取 [**要求格式**]。 按一下 **[下一步]**。

6.  在 [**憑證資訊**] 頁面上，按一下 [**詳細資料**]，然後按一下 [**屬性**]。

7.  在 [**證書****摘要**] 索引標籤上的 [**易記名稱**] 欄位中，輸入此憑證的名稱。 您也可以選擇在 [**描述**] 欄位中輸入描述。 系統管理員通常會使用易記名稱和描述來識別證書用途，例如**Lync Server 的反向 Proxy 監聽**程式。

8.  選取 [**主語**] 索引標籤。在**類型**的 [主旨**名稱**] 底下，選取 [主旨名稱] 類型的 [**通用名稱**]。 針對 [**值**] 輸入您將用於反向 proxy 的主旨名稱，然後按一下 [**新增**]。 在本主題中的資料表中所提供的範例中，subject 名稱是 webext.contoso.com，並會在主旨名稱的 [值] 欄位中輸入。

9.  在 [ **Subject** ] 索引標籤的 [**替代名稱**] 底下，從下拉式清單中選取 [ **DNS** **]。** 針對您在憑證上所需的每個已定義的消費者替換名稱，輸入完整的功能變數名稱，然後按一下 [**新增**]。 例如，在資料表中有三個使用中的主題替換名稱、meet.contoso.com、dialin.contoso.com 和 lyncdiscover.contoso.com。 在 [**值**] 欄位中，輸入 meet.contoso.com，然後按一下 [**新增**]。 針對您需要定義的每個主體替換名稱，重複上述步驟。

10. 在 [**憑證屬性**] 頁面上，按一下 [**延伸**] 索引標籤。在此頁面上，您將在**金鑰用法**中定義加密金鑰的目的，以及**延伸金鑰用法（應用程式原則）** 中的延伸金鑰用法。

11. 按一下 [**金鑰用法**] 箭號，以顯示**可用的選項**。 按一下 [可用選項] 底下的 [**數位簽章**]，然後按一下 [**新增**]。 按一下 [**金鑰解碼**]，然後按一下 [**新增**]。 如果未選取 [**將這些主要用法設為重要**] 核取方塊，請選取該核取方塊。

12. 按一下 [**擴展金鑰用法（應用程式原則）** ] 箭號，以顯示**可用的選項**。 按一下 [可用選項] 底下的 [**伺服器驗證**]，然後按一下 [**新增**]。 按一下 [**用戶端驗證**]，然後按一下 [**新增**]。 如果已選取 [**使延伸金鑰用法為關鍵性**] 核取方塊，請取消選取核取方塊。 與 [金鑰用法] 核取方塊（必須核取）相反，您必須確定未選取 [延伸金鑰用法] 核取方塊。

13. 在 [**憑證屬性**] 頁面上，按一下 [**私人金鑰**] 索引標籤。按一下 [**金鑰選項**] 箭號。 針對**金鑰大小**，請從下拉式清單中選取 [ **2048** ]。 如果您要在並非此憑證所針對的相反代理伺服器以外的電腦上產生此金鑰組與 CSR，請選取 [**讓私人金鑰可匯出**]。
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="安全性" alt="security" />安全性注意事項：</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>當您在伺服器陣列中有多個反向 proxy 時，通常會建議選取 [<strong>製作私密金鑰匯出</strong>]，因為您會將憑證和私密金鑰複製到伺服器陣列中的每個電腦。 如果您允許可匯出的私密金鑰，您就必須對憑證以及它產生的電腦格外小心。 如果密碼遭到破壞，私密金鑰會將 [無法使用] 轉譯成無法使用，而且可能會將電腦或電腦暴露在外部存取及其他安全性漏洞。</td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. 在 [**私人金鑰**] 索引標籤上，按一下 [**金鑰類型**] 箭號。 選取 [ **Exchange** ] 選項。

15. 按一下 **[確定]** 儲存已設定的**憑證屬性**。

16. 在 [**憑證註冊**] 頁面上，按一下 **[下一步]**。

17. 在 [**您要儲存離線要求的位置？** ] 頁面上，系統會提示您輸入**檔案名和****檔案格式**，以儲存憑證簽署要求。

18. **在 [檔案名專案]** 欄位中，輸入要求的路徑和檔案名，或按一下 **[流覽]** 以選取檔案的位置，然後輸入要求的檔案名。

19. 針對**檔案格式**，請按一下 [**基本 64** ] 或 [**二進位**]。 除非您向您的憑證提供給供應商的指示，否則請選取 [**基本 64** ]。

20. 找出您在上一個步驟中儲存的要求檔案。 提交至您的公用憑證授權單位。
    
    <div>
    

    > [!IMPORTANT]
    > Microsoft 已識別符合整合通訊需求的公用 Ca。 下列知識庫文章中會保留清單。 <A href="http://go.microsoft.com/fwlink/?linkid=282625">http://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

