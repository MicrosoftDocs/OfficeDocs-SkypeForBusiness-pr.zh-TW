---
title: Lync Server 2013：回應群組設定權限和先決條件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcf10a61ed5285fe5cfc907c2624a14112d96eae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a>Lync Server 2013 中的回應群組設定權限和先決條件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

[回應] 群組是企業語音通話管理功能。 本主題描述您必須具備的位置，才能設定回應群組以及執行設定工作所需的管理認證及許可權。

本節假設您已閱讀與回應群組相關的規劃檔。 如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 規劃通話管理功能](lync-server-2013-planning-for-call-management-features.md)。

<div>

## <a name="configuration-tools-and-administrative-roles"></a>組態工具與管理角色

您可以使用下列管理工具來設定回應群組：

  - Lync Server 控制台

  - 回應群組設定工具

  - Lync Server 管理命令介面

若要設定回應群組，您必須是下列至少一個管理角色的成員：


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Active Directory 安全性群組（1）</strong></p></td>
<td><p>建立工作流程</p></td>
<td><p>指派管理員</p></td>
<td><p>建立/assign 代理程式、佇列</p></td>
<td><p>建立/管理假日與上班時間</p></td>
<td><p>啟動/停用工作流程</p></td>
<td><p>設定工作流程（IVR 或查尋群組）</p></td>
</tr>
<tr class="even">
<td><p><strong>CsResponseGroupAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsResponseGroupManager</strong></p></td>
<td> </td>
<td><p>√（2）</p></td>
<td><p>√（3）</p></td>
<td><p>√（3）</p></td>
<td><p>√（3）</p></td>
<td><p>√（3）</p></td>
</tr>
<tr class="even">
<td><p><strong>CsVoiceAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsServerAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="even">
<td><p><strong>CsAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsViewOnlyAdministrator</strong></p></td>
<td><p>√（4）</p></td>
<td><p>√（4）</p></td>
<td><p>√（4）</p></td>
<td><p>√（4）</p></td>
<td><p>√（4）</p></td>
<td><p>√（4）</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>（1）</STRONG> Active Directory 網域服務使用者物件必須是所列指定 Active directory 安全性群組的成員。 具有適當許可權的系統管理員或其他受委派 Active Directory 群組成員（例如，管理員、帳戶操作員）必須將使用者物件新增至所列的安全群組或群組，使用者才能執行所列的函數。 <STRONG>（2）</STRONG>僅適用于 CsResponseGroupAdministrator 已指派給 CsResponseGroupManager 的工作流程。 <STRONG>（3）</STRONG>回應群組管理員可以將 CsResponseGroupManager 的另一個成員指派給目前管理員已管理的工作流程。 <STRONG>（4）</STRONG> CsViewOnlyAdministrator 只能執行動詞「取得」 Lync Server 管理命令介面 Cmdlet。



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a>回應群組設定的先決條件

回應群組需要下列元件：

  - 應用程式服務

  - 回應群組應用程式

  - 語言套件

  - 檔案存放區（儲存音訊檔案）

  - Web 服務（包括回應群組設定工具以及代理程式的登入和登出主機）

當您部署企業語音時，系統會預設安裝這些元件。

在設定回應群組之前，您可能需要執行下列工作：

  - 允許使用者使用 Lync Server 2013 和企業版語音。

  - 修改要與聯邦資訊處理標準（FIPS）相容的設定檔。

  - 修改資料庫排序規則，以支援佇列名稱和代理群組名稱的 Yi、Meng 及 Zang 字元。

<div>

## <a name="enabling-users"></a>啟用使用者

配置回應群組的第一個步驟是建立代理群組。 在您可以建立代理群組之前，您必須先啟用將擁有 Lync Server 2013 和 Enterprise Voice 之回應群組的使用者。 啟用 Lync Server 2013 的使用者通常是企業版 server 或標準版伺服器部署中的一個步驟。 如需有關啟用 Lync Server 2013 使用者的詳細資料，請參閱[停用或重新啟用 Lync server 2013 的使用者帳戶](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)。 啟用企業語音的使用者通常是企業語音部署中的一個步驟。 如需詳細資訊，請參閱[在 Lync Server 2013 中啟用企業語音的使用者](lync-server-2013-enable-users-for-enterprise-voice.md)。

</div>

<div>

## <a name="complying-with-fips-requirements"></a>遵守 FIPS 需求

本節僅適用于您的組織必須遵循聯邦資訊處理標準（FIPS）的情況。

若要符合 FIPS，您必須在安裝 Web 服務之後，修改應用程式層級的 web.config 檔案，以使用不同的密碼演算法。 您必須指定 ASP.NET 使用 [三重資料加密標準（3DES）] 演算法來處理檢視狀態資料。 針對回應群組應用程式，此需求會套用至回應群組設定工具以及代理程式登入和登出主機。 如需此需求的詳細資料，請參閱 Microsoft 知識庫文章911722：當您在從 ASP.NET 1.1 升級至 ASP.NET 2.0 之後，當您存取已啟用 ViewState 的 ASP.NET 網頁時，您可能會[http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183)收到錯誤訊息。

若要修改 web.config 檔案，請執行下列動作：

1.  在記事本等文字編輯器中，開啟應用程式層級的 web.config 檔案。

2.  在 web.config 檔案中，找到該`<system.web>`節。

3.  在`<system.web>`區段中`<machineKey>`新增下列區段：
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  儲存 web.config 檔案。

5.  在命令提示字元執行下列命令，以重新開機網際網路資訊服務（IIS）服務：
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a>支援 Yi、Meng 和 Zang 字元

本節僅適用于您的組織必須支援 Yi、Meng 或 Zang 字元的情況。

<div>


> [!NOTE]  
> 如需彝語、Meng 和 Zang 字元的用途，以及它們對於您的部署而言可能很重要的原因，請參閱 GB18030 字元集合<A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>上的資訊。



</div>

若要支援 Yi、Meng 或 Zang 字元，您必須修改 Rgsconfig 資料庫的排序規則。 在每個 Rgsconfig 資料庫的下清單格中，變更 [**名稱**] 資料行的排序規則：

  - 擁有者.AgentGroups

  - 擁有者.BusinessHours

  - 擁有者.HolidaySets

  - 擁有者.佇列

  - 擁有者.工作流程

針對 SQL Server 2008 R2 與 SQL Server 2012，請使用拉丁語\_一般\_100 （區分重音）排序規則。 如果您使用此排序規則，則所有物件名稱都不區分大小寫。

您可以使用 Microsoft SQL Server Management Studio 變更排序規則。 如需使用此工具的詳細資訊，請參閱「使用 SQL Server Management [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184)Studio」。 請依照下列步驟變更排序規則：

1.  確定 SQL Server Management Studio 已設定為允許重新建立需要資料表的變更。 如需詳細資訊，請參閱「儲存（不允許）對話方塊[http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186)」。 如需有關設定欄排序規則的詳細資訊，請參閱「如何：設定欄排序規則（視覺化資料庫[http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185)工具）」。

2.  使用 Microsoft SQL Server Management Studio 連接到 Rgsconfig 資料庫。

3.  在 Rgsconfig 資料庫中尋找您要變更的資料表，以滑鼠右鍵按一下資料表，然後按一下 [**設計**]。

4.  變更 [**名稱**] 資料行的排序規則，並儲存資料表。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

