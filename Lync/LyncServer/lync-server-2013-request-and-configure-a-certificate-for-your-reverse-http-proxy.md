---
title: 要求以及設定反向 HTTP proxy 的憑證
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
ms.openlocfilehash: 9c380cb67e1e156bef616f81ce0c42f699b472d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a>要求以及設定反向 HTTP proxy Lync Server 2013 中的憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-14_

您必須執行 Microsoft Forefront Threat Management Gateway 2010 或 IIS ARR 到執行 Microsoft Lync 的內部伺服器發出伺服器憑證的 CA 基礎結構的伺服器上安裝根憑證授權單位 (CA) 憑證Server 2013。

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
<td><p>選用 Director Web 服務 （如果部署 Director）</p></td>
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
> 如果您同時使用 Microsoft Exchange Server 您也必須設定 Exchange 自動探索和 web 服務 url 的反向 proxy 規則。

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

您的反向 proxy 上建立憑證要求。 在另一部電腦上建立要求，但您必須使用私密金鑰匯出的簽署的憑證並匯入反向 proxy，一旦您有來自公用憑證授權單位。

<div>


> [!NOTE]
> 憑證要求或憑證簽署要求 (CSR) 是以驗證並登入要求的電腦公開金鑰受信任的公用憑證授權單位 (CA) 的要求。 產生憑證時，會建立公開金鑰及私密金鑰。 僅限公開金鑰共用且帶正負號。 顧名思義，公開金鑰是提供給任何公用的要求。 公開金鑰是供用戶端、 伺服器和其他需要安全地交換資訊，並驗證電腦的身分識別的要求。 私密金鑰會保持安全，並只能由建立來解密郵件以其公開金鑰加密金鑰組的電腦。 私密金鑰可以用於其他用途。 反向 proxy 的目的，資料編密是主要的使用。 再，憑證重要層級的憑證驗證是另一種用法，且只限於驗證已要求者電腦的公開金鑰，或您有公開金鑰的電腦是實際其所宣稱的電腦。



</div>

<div>


> [!TIP]
> 如果您規劃您的 Edge Server 憑證和反向 proxy 憑證在同一時間時，您應該注意到已有極大的兩個憑證需求之間的相似性。 當您設定，並要求您的 Edge Server 憑證時，合併 Edge Server 和反向 proxy 的主體替代名稱。 如果您匯出憑證與私密金鑰和將匯出的檔案複製到反向 proxy 然後匯入的憑證/金鑰組並將其指派視即將來臨的程序，您可以使用您的反向 proxy 的相同的憑證。 Edge Server 的憑證需求，請參閱&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">Lync Server 2013 中的 Edge Server 憑證計劃</A>及反向 proxy<A href="lync-server-2013-certificate-summary-reverse-proxy.md">憑證摘要-Lync Server 2013 中的反向 proxy</A>。 請確定您建立具可匯出的私密金鑰的憑證。 建立具可匯出的私密金鑰的憑證與憑證要求才區的 Edge Server，因此這是標準的作法是，並在 Edge Server 的 [Lync Server 部署精靈的 [憑證] 精靈可讓您設定<STRONG>進行可匯出的私密金鑰</STRONG>的旗標。 一旦您從公用憑證授權單位取回收到憑證要求，您將會匯出憑證與私密金鑰。 主題中的<A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Lync Server 2013 的外部 edge 介面的憑證設定</A>如需如何建立並匯出憑證與私密金鑰的詳細資訊，請參閱 「 若要匯出憑證與私密金鑰的集區中的 Edge Server 」 一節。 類型<STRONG>.pfx</STRONG>應該是憑證的擴充。



</div>

若要產生的憑證簽署要求，其中會指派的憑證及私密金鑰的電腦上，您執行下列動作：

**建立的憑證簽署要求**

1.  開啟 Microsoft Management Console (MMC)，並新增憑證嵌入式管理單元中，選取 [**電腦**]，然後依序展開 [**個人**。 如需如何建立憑證] 主控台中的 [Microsoft Management Console (MMC) 的詳細資訊，請參閱[https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616)。

2.  **憑證**上按一下滑鼠右鍵，按一下 [**所有工作**，按一下都 [**進階作業**，按一下都 [**建立自訂要求**。

3.  在**憑證註冊**頁面上，按一下 [**下一步**]。

4.  在 [**自訂要求****選取憑證註冊原則**] 頁面上，選取 [**沒有註冊原則繼續**。 按 [下一步]****。

5.  在 [**自訂要求**] 頁面上的**範本**選取 **（沒有範本） 傳統金鑰**。 除非另有指示您的憑證提供者，將保留**抑制預設延伸**未勾選和**要求格式**的選取範圍上**PKCS \#10**。 按 [下一步]****。

6.  在 [**認證資訊**] 頁面上，按一下 [**詳細資料**，然後按 [**屬性**。

7.  在 [**易記名稱**] 欄位中的 [**一般**] 索引標籤上的**憑證內容**] 頁面上，輸入此憑證的名稱。 （選用） 在 [**描述**] 欄位中輸入描述。 易記的名稱和描述是通常用於由系統管理員識別憑證用途為何，例如 [ **Lync Server 的反向 Proxy 接聽程式**。

8.  選取 [**主旨**] 索引標籤。**類型**的**主體名稱**] 下選取 [主旨名稱類型的**一般名稱**。 **值**中，輸入將用於反向 proxy，然後按一下 [**新增**的主體名稱。 在本主題中的表格中所提供的範例，在主體名稱是 webext.contoso.com，而要輸入到主體名稱的 [值] 欄位。

9.  **替代名稱**下的 [**主旨**] 索引標籤中，選取 [ **DNS**從下拉式清單向下的**類型**。 每個已定義的主體替代名稱，您需要在憑證上，輸入完整的網域名稱，然後按一下 [**新增**]。 例如，在資料表中有三個主體替代名稱、 meet.contoso.com、 dialin.contoso.com 和 lyncdiscover.contoso.com。 在 [**值**] 欄位中的 [類型 meet.contoso.com，然後按一下 [**新增**。 重複針對每個您要定義的主體替代名稱。

10. 在**憑證內容**頁面上，按一下 [**延伸**] 索引標籤。在此頁面上，您將**金鑰使用方法**和延伸的金鑰使用**延伸**的機碼使用量 （應用程式原則]） 中定義的密碼編譯的主要目的。

11. 按一下 [**機碼流量**箭號，以顯示**可用的選項**。 [可用的選項] 下按一下 [**數位簽章**]，然後按一下 [**新增**]。 按一下 [**金鑰加密**，然後按一下 [**新增**]。 如果未選取**進行重大這些金鑰使用方式**的核取方塊，選取核取方塊。

12. 按一下 [**延伸金鑰使用方法 （應用程式原則）** 箭號，以顯示**可用的選項**。 [可用的選項] 下按一下 [**伺服器驗證**，然後按一下 [**新增**]。 按一下 [**用戶端驗證**]，然後按一下 [**新增**]。 如果會檢查**進行擴充金鑰使用方式重要**核取方塊，取消選取該核取方塊。 相反金鑰使用方式] 核取方塊 （其必須檢查） 您必須確定已不存延伸金鑰使用方式] 核取方塊。

13. 在 [**憑證內容**] 頁面上，按一下 [**私密金鑰**] 索引標籤按一下 [**金鑰選項**] 箭號。 若是**金鑰大小**，請選取 [ **2048年**從下拉式清單向下。 如果您要產生此金鑰組和 CSR，供此憑證的反向 proxy 以外的電腦上，選取 [設定**成可匯出的私密金鑰**。
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="安全性" alt="security" />安全性附註：</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>當您將有一個以上的反向 proxy 伺服器陣列中，因為您會將憑證與私密金鑰複製到伺服器陣列中每一部機器通常建議您選取 [<strong>讓可匯出的私密金鑰</strong>。 如果您不要允許可匯出的私密金鑰，您必須小心憑證與它產生的電腦。 私密金鑰]，如果危害，將會轉譯憑證沒有用，以及可能會公開外部存取及其他安全性弱點的電腦。</td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. **私密金鑰**索引標籤上，按一下 [**索引鍵類型**箭號。 選取 [ **Exchange** ] 選項。

15. 按一下 **[確定]** 以儲存您已設定**憑證內容**]。

16. 在**憑證註冊**頁面上，按一下 [**下一步**]。

17. 在**您要在其中儲存離線要求？** ] 頁面上，系統會提示您輸入**檔案名稱**和**檔案格式**儲存的憑證簽署要求。

18. 在 [**檔案名稱**項目] 欄位中，輸入路徑和檔名的要求，或按一下 [**瀏覽**至選取的檔案的位置，然後輸入要求的檔案名稱。

19. **檔案格式**，請按一下**Base 64** ] 或 [**二進位**。 除非您另有指示，否則廠商針對您的憑證，請選取 [ **Base 64** ]。

20. 找出您在上一個步驟中儲存的要求檔案。 送出至您的公用憑證授權單位。
    
    <div>
    

    > [!IMPORTANT]
    > Microsoft 已識別公用 Ca 符合整合通訊用途的需求。 清單會維護下列知識庫文章中。 <A href="https://go.microsoft.com/fwlink/?linkid=282625">https://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

