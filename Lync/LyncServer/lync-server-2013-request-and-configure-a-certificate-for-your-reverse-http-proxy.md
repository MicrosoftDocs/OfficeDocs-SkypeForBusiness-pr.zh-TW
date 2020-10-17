---
title: 要求和設定反向 HTTP proxy 的憑證
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
ms.openlocfilehash: 7651e3da61e5ca197d36ca59ad8216af4c0188af
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511980"
---
# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a>在 Lync Server 2013 中要求和設定反向 HTTP proxy 的憑證

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-14_

在對執行 Microsoft Lync Server 2013 的內部伺服器發出伺服器憑證的 CA 基礎結構上，，您必須在執行 Microsoft Forefront 威脅管理閘道2010或 IIS ARR 的伺服器上，安裝根憑證授權單位 (CA) 憑證。

您也必須在反向 Proxy 伺服器上安裝公用 Web 伺服器憑證。此憑證的主體替代名稱應該包含已啟用遠端存取的使用者所在之每個集區的已發行外部完整網域名稱 (FQDN)，以及要在該 Edge 基礎結構內使用之所有 Director 或 Director 集區的 FQDN。主體替代名稱也必須包含會議簡單 URL、撥入簡單 URL，以及 (如果您要部署行動應用程式，並且計劃要使用自動探索) 外部自動探索服務 URL，如下表所示。


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
<td><p>主體名稱</p></td>
<td><p>集區 FQDN</p></td>
<td><p>webext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>主體替代名稱</p></td>
<td><p>集區 FQDN</p></td>
<td><p>webext.contoso.com</p>



> [!IMPORTANT]
> 主體名稱也必須出現在主體替代名稱中。

</td>
</tr>
<tr class="odd">
<td><p>主體替代名稱</p></td>
<td><p>在部署 Director 時 (選用 Director Web 服務) </p></td>
<td><p>webdirext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>主體替代名稱</p></td>
<td><p>會議簡單 URL</p>



> [!NOTE]
> 所有會議簡單 URL 都必須出現在主體替代名稱中。每個 SIP 網域都至少必須有一個作用中的會議簡單 URL。

</td>
<td><p>meet.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>主體替代名稱</p></td>
<td><p>Dial-in 簡單 URL</p></td>
<td><p>dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>主體替代名稱</p></td>
<td><p>Office Web Apps Server</p></td>
<td><p>officewebapps01.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>主體替代名稱</p></td>
<td><p>外部自動探索服務 URL</p></td>
<td><p>lyncdiscover.contoso.com</p>



> [!NOTE]
> 如果您也是使用 Microsoft Exchange Server，您也需要為 Exchange 自動探索和 web 服務 URLs 設定反向 proxy 規則。

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> 如果您的內部部署包含多個 Standard Edition Server 或前端集區，則您必須為每個外部 Web 伺服陣列 FQDN 設定 Web 發行規則，且需要針對其中每個 FQDN 各有一個憑證和網頁接聽程式，否則，您就必須取得憑證 (其主體替代名稱包含所有集區使用的名稱)、將憑證指派給網頁接聽程式，然後在多個 Web 發行規則之間共用憑證。



</div>

<div>

## <a name="create-a-certificate-request"></a>建立憑證要求

在反向 proxy 上建立憑證要求。 您可以在另一部電腦上建立要求，但是必須使用私密金鑰匯出簽署的憑證，並在從公用憑證授權單位單位收到該憑證後，再將其匯入到反向 proxy。

<div>


> [!NOTE]
>  (CSR) 的憑證要求或憑證簽署要求 (CA) 以驗證要求的電腦的公開金鑰，並對信任的公用憑證授權單位單位要求。 當憑證產生時，即會建立公開金鑰和私密金鑰。 只會共用和簽署公開金鑰。 顧名思義，公開金鑰可供任何公開要求使用。 公開金鑰可供用戶端、伺服器及其他要求者使用，以安全地交換資訊和驗證電腦的身分識別。 私密金鑰是保持安全的，而且只由建立金鑰組的電腦使用，用來解密以其公開金鑰加密的郵件。 私密金鑰可用於其他用途。 針對反向 proxy 目的，資料加密是主要用途。 Secondarily，憑證機碼層級的憑證驗證是另一個用途，而且只限于要求申請者具有電腦公開金鑰的驗證，或您具有公開金鑰的電腦實際上是其所宣告的電腦。



</div>

<div>


> [!TIP]
> 如果您同時規劃 Edge Server 憑證和反向 proxy 憑證，您應該注意到這兩種憑證需求具有極大的相似性。 當您設定和要求 Edge Server 憑證時，請結合 Edge Server 與反向 proxy 主體的替代名稱。 如果您匯出憑證和私密金鑰，並將匯出的檔案複製到反向 proxy，然後匯入憑證/金鑰組，並在即將進行的程式中將其指派給，您可以對反向 proxy 使用相同的憑證。 請參閱 lync server 2013 中的 edge server Plan Edge server Plan 的憑證需求 &nbsp; <A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan for Edge Server certificates in Lync Server 2013</A>和 lync server 2013 中的反向 proxy<A href="lync-server-2013-certificate-summary-reverse-proxy.md">憑證摘要-反向</A>proxy。 請務必使用可匯出的私密金鑰來建立憑證。 您可以使用可匯出的私密金鑰建立憑證和憑證要求，以用於集區的 Edge Server，因此這是一般作法，而在 Edge Server 的 Lync Server 部署嚮導中的憑證嚮導可讓您設定 <STRONG>私密金鑰可匯出</STRONG> 的標誌。 當您從公用憑證授權單位發回憑證要求後，就會匯出憑證和私密金鑰。 如需如何使用私密金鑰建立及匯出憑證的詳細資訊，請參閱本 <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">2013</A> 主題中的「使用集區中 Edge server 的私密金鑰來匯出憑證」一節中的 [匯出憑證]。 憑證的副檔名應該是 <STRONG>.pfx</STRONG>的類型。



</div>

若要在將指派憑證和私密金鑰的電腦上產生憑證簽署要求，請執行下列操作：

**建立憑證簽署要求**

1.  開啟 Microsoft Management Console (MMC) 並新增 [憑證] 嵌入式管理單元，然後選取 [ **電腦**]，然後展開 [ **個人**]。 如需如何在 Microsoft Management Console (MMC) 中建立憑證主控台的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616) 。

2.  以滑鼠右鍵按一下 [ **憑證**]，按一下 [ **所有**工作]，按一下 [ **高級作業**]，按一下 [ **建立自訂要求**]

3.  在 [ **憑證註冊** ] 頁面上，按 **[下一步]**。

4.  在 [**自訂要求**] 底下的 [**選取憑證註冊原則**] 頁面上，選取 [**繼續，不含註冊原則**] 按 **[下一步]**。

5.  在 [ **自訂要求** ] 頁面上，針對 **範本** 選取 [ ** (沒有範本) 舊版金鑰**]。 除非您的憑證提供者其他方式使用，否則請保留**取消勾選預設的分機**號碼，並在**PKCS \# 10**上選取**要求格式**。 按 **[下一步]**。

6.  在 [ **憑證資訊** ] 頁面上，按一下 [ **詳細資料**]，然後按一下 [ **屬性**]。

7.  在 [**憑證屬性**] 頁面上的 [**好記名稱**] 欄位中，輸入此**憑證的名稱**。 （選用）在 [ **描述** ] 欄位中輸入描述。 「好記名稱」和「描述」通常是由系統管理員用來識別憑證用途，例如 **Lync Server 的反向 Proxy 監聽器**。

8.  選取 [**主旨**] 索引標籤。在 [**類型**的**主體名稱**] 底下，選取 [主體名稱] 類型的 [**一般名稱**]。 針對 **值**輸入您將用於反向 proxy 的主體名稱，然後按一下 [ **新增**]。 在本主題的表格中所提供的範例中，主體名稱是 webext.contoso.com，並會輸入至 [主旨名稱] 的 [值] 欄位中。

9.  在 [**替代名稱**] 下的 [主旨] 索引標籤上，從下拉式清單中**選取 [** **DNS** **]。** 針對憑證上所需的每個已定義的主體替代名稱，輸入完整的功能變數名稱，然後按一下 [ **新增**]。 例如，在資料表中有三個主體替代名稱、meet.contoso.com、dialin.contoso.com 及 lyncdiscover.contoso.com。 在 [ **值** ] 欄位中，輸入 meet.contoso.com，然後按一下 [ **新增**]。 針對您需要定義的每個主體替代名稱重複此名稱。

10. 在 [ **憑證屬性** ] 頁面上，按一下 [ **副檔名** ] 索引標籤。在此頁面上，您會定義 **金鑰用法** 中的加密金鑰用途，以及 **延伸金鑰使用 (應用程式原則) **中的延伸金鑰用法。

11. 按一下 [ **金鑰使用** ] 箭頭以顯示 **可用的選項**。 在 [可用選項] 底下，按一下 [ **數位簽章**]，然後按一下 [ **新增**]。 按一下 [ **金鑰解碼**]，然後按一下 [ **新增**]。 如果未選取 [ **將這些按鍵用法** 設定為關鍵的核取方塊] 核取方塊，請選取核取方塊。

12. 按一下 [ **擴充金鑰用法] (應用程式原則) ** 箭號以顯示 **可用的選項**。 在 [可用選項] 底下，按一下 [ **伺服器驗證**]，然後按一下 [ **新增**]。 按一下 [ **用戶端驗證**]，然後按一下 [ **新增**]。 如果已勾選 [ **將擴充金鑰使用** 方式設定為重要的] 核取方塊，請取消選取此核取方塊。 不是必須檢查的 [主要使用狀況] 核取方塊 () 您必須確定未勾選 [擴充金鑰使用狀況] 核取方塊。

13. 在 [ **憑證屬性** ] 頁面上，按一下 [ **私密金鑰** ] 索引標籤。按一下 [ **按鍵選項** ] 箭頭。 針對 **金鑰大小**，從下拉式功能表中選取 [ **2048** ]。 若要在此憑證所針對的反向 proxy 以外的電腦上產生此金鑰組和 CSR，請選取 [ **讓私密金鑰可匯出**]。
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" />安全性附注：</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>當您在伺服器陣列中有一個以上的反向 proxy 時，如果您要將憑證和私密金鑰複製到伺服器陣列中的每一部電腦，則通常會建議選取 [ <strong>讓私密金鑰可匯出</strong> ]。 如果您確實允許可匯出的私密金鑰，您必須特別小心憑證和其產生所在的電腦。 私密金鑰（如已遭破壞）將會使憑證無法使用，而且可能會將電腦或電腦公開給外部存取和其他安全性弱點。</td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. 在 [ **私密金鑰** ] 索引標籤上，按一下 [ **Key type** ] 箭頭。 選取 [ **Exchange** ] 選項。

15. 按一下 **[確定]** 儲存您已設定的 **憑證屬性** 。

16. 在 [ **憑證註冊** ] 頁面上，按 **[下一步]**。

17. 在 [ **您要用來儲存離線要求的位置** ] 頁面上，系統會提示您 **輸入檔案名，以及儲存** 憑證簽署要求的 **檔案格式** 。

18. **在 [檔案名專案]** 欄位中，輸入要求的路徑和檔案名，或按一下 **[流覽]** 以選取檔案的位置，然後輸入要求的檔案名。

19. 針對 **檔案格式**，按一下 [ **基底 64** ] 或 [ **二進位**]。 選取 [ **基本 64** ]，除非您的憑證的廠商未另行指示。

20. 找到您在上一個步驟中儲存的要求檔案。 提交至您的公用憑證授權單位單位。
    
    <div>
    

    > [!IMPORTANT]
    > Microsoft 已識別出符合整合通訊目的需求的公用 Ca。 下列知識文庫文章中會維護清單。 <A href="https://go.microsoft.com/fwlink/?linkid=282625">https://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

