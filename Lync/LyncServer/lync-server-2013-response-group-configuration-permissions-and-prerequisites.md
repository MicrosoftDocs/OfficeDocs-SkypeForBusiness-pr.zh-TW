---
title: Lync Server 2013：回應群組設定許可權和必要條件
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
ms.openlocfilehash: 7289b8818a6193efa867ab0a8671abf6d4701f7c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511740"
---
# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a>Lync Server 2013 的回應群組設定許可權和必要條件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

「回應群組」是企業語音的一項通話管理功能。本主題說明設定回應群組之前需要具有的項目，以及執行設定工作所需的系統管理認證和權限。

本節假設您已閱讀與回應群組相關的規劃文件。 如需詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的通話管理功能](lync-server-2013-planning-for-call-management-features.md) 。

<div>

## <a name="configuration-tools-and-administrative-roles"></a>設定工具與系統管理角色

您可以使用下列系統管理工具來設定回應群組：

  - Lync Server 控制台

  - 回應群組設定工具

  - Lync Server 管理命令介面

若要設定回應群組，您至少必須是下列其中一個系統管理角色的成員：


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
<td><p><strong>Active Directory 安全性群組 (1)</strong></p></td>
<td><p>建立工作流程</p></td>
<td><p>指派管理員</p></td>
<td><p>建立/指派代理人和佇列</p></td>
<td><p>建立/管理假日和營業時間</p></td>
<td><p>啟用/停用工作流程</p></td>
<td><p>設定工作流程 (IVR 或群組搜尋)</p></td>
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
<td><p>√ (2) </p></td>
<td><p>√ (3) </p></td>
<td><p>√ (3) </p></td>
<td><p>√ (3) </p></td>
<td><p>√ (3) </p></td>
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
<td><p>√ (4) </p></td>
<td><p>√ (4) </p></td>
<td><p>√ (4) </p></td>
<td><p>√ (4) </p></td>
<td><p>√ (4) </p></td>
<td><p>√ (4) </p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG> (1) </STRONG> Active Directory 網域服務使用者物件必須是所列指定之 Active Directory 安全性群組的成員。 具有適當許可權的系統管理員或其他委派的 Active Directory 群組成員，可將使用者新增至安全性群組中 (例如，系統管理員、帳戶操作員) 必須將使用者物件新增至所列的安全性群組或群組，使用者才能執行所列的功能。 <STRONG> (2) </STRONG> 僅適用于 CsResponseGroupAdministrator 已指定給 CsResponseGroupManager 的工作流程。 <STRONG> (3) </STRONG> 回應群組管理員可以將 CsResponseGroupManager 的另一個成員指派給目前管理員已管理的工作流程。 <STRONG> (4) </STRONG> CsViewOnlyAdministrator 只能執行動詞 "Get" Lync Server 管理命令介面 Cmdlet。



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a>回應群組設定先決條件

回應群組需要下列元件：

  - 應用程式服務

  - 回應群組應用程式

  - 語言套件

  - 檔案存放區 (用於保留音訊檔案)

  - Web 服務 (包含回應群組設定工具和代理程式的登入和登出主控台) 

當您部署企業語音時，預設會安裝上述所有元件。

在設定回應群組之前，您可能需要先執行下列工作：

  - 為使用者啟用 Lync Server 2013 和 Enterprise Voice。

  - 修改組態檔，以符合美國聯邦資訊處理標準 (FIPS)。

  - 修改資料庫定序，以支援佇列名稱和代理人群組名稱中的 Yi、Meng 和 Zang 字元。

<div>

## <a name="enabling-users"></a>啟用使用者

設定回應群組的第一個步驟是建立代理人群組。 在您可以建立代理人群組之前，您必須啟用將成為 Lync Server 2013 和 Enterprise Voice 之回應群組之代理人的使用者。 為 Lync Server 2013 啟用使用者通常是 Enterprise Edition server 或 Standard Edition server 部署中的一個步驟。 如需對 Lync Server 2013 啟用使用者的詳細資訊，請參閱 [Disable or 重新啟用 Lync server 2013 的使用者帳戶](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)。 啟用使用者的企業語音一般是企業語音部署中的步驟。 如需詳細資訊，請參閱 [Enable users For Enterprise Voice In Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)。

</div>

<div>

## <a name="complying-with-fips-requirements"></a>遵守 FIPS 要求

只有在您的組織需要遵守美國聯邦資訊處理標準 (FIPS) 時，才適用本節內容。

若要遵守 FIPS，您需要修改應用程式層級的 Web.config 檔案，以在安裝 Web 服務後使用不同的密碼編譯演算法。 您需要指定 ASP.NET 使用三重資料加密標準 (3DES) 演算法來處理檢視狀態資料。 針對回應群組應用程式，此需求適用于回應群組設定工具和代理程式登入和登出主控台。 如需此需求的詳細資訊，請參閱 Microsoft 知識庫文章911722：「當您存取從 ASP.NET 1.1 升級為 ASP.NET 2.0 的 ASP.NET 網頁 ViewState 時，可能會收到錯誤訊息，"at] [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkid=196183) 。

若要修改 Web.config 檔案，請執行下列動作：

1.  在文字編輯器 (如 [記事本]) 中，開啟應用程式層級的 Web.config 檔案。

2.  在 Web.config 檔案中，找出 `<system.web>` 區段。

3.  `<machineKey>`在區段中新增下列區段 `<system.web>` ：
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  儲存 Web.config 檔案。

5.  在命令提示字元中執行下列命令，以重新開機網際網路資訊服務 (IIS) 服務：
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a>支援 Yi、Meng 和 Zang 字元

只有在您的組織需要支援 Yi、Meng 或 Zang 字元時，才適用本節內容。

<div>


> [!NOTE]  
> 如需有關彝語、Meng 及 Zang 字元的資訊及其可能對您的部署很重要的原因，請參閱 GB18030 字元集上的資訊 <A href="https://go.microsoft.com/fwlink/p/?linkid=240223">https://go.microsoft.com/fwlink/p/?linkId=240223</A> 。



</div>

若要支援 Yi、Meng 或 Zang 字元，您需要修改 Rgsconfig 資料庫的定序。請變更每個 Rgsconfig 資料庫中下列各資料表內 **[名稱]** 資料行的定序：

  - Dbo。AgentGroups

  - Dbo。BusinessHours

  - Dbo。HolidaySets

  - Dbo。佇列

  - Dbo。流程

針對 SQL Server 2008 R2 和 SQL Server 2012，使用拉丁語 \_ 一般 \_ 100 (區分重音) 歸類。 如果您使用此定序，則所有物件名稱都不區分大小寫。

您可以使用 Microsoft SQL Server Management Studio 來變更定序。 如需使用此工具的詳細資訊，請參閱「使用 SQL Server Management Studio」 [https://go.microsoft.com/fwlink/p/?linkId=196184](https://go.microsoft.com/fwlink/p/?linkid=196184) 。 請遵循下列步驟來變更定序：

1.  確定 SQL Server Management Studio 已設成允許需要重建資料表的變更。 如需詳細資訊，請參閱的「儲存 (不允許) 對話方塊」 [https://go.microsoft.com/fwlink/p/?linkId=196186](https://go.microsoft.com/fwlink/p/?linkid=196186) 。 如需設定欄歸類的詳細資訊，請參閱 how to： Set Column 歸類 (Visual Database Tools) "at" [https://go.microsoft.com/fwlink/p/?linkId=196185](https://go.microsoft.com/fwlink/p/?linkid=196185) 。

2.  使用 Microsoft SQL Server Management Studio 連線至 Rgsconfig 資料庫。

3.  在 Rgsconfig 資料庫中找到想要變更的資料表，並用滑鼠右鍵按一下資料表，然後按一下 **[設計]**。

4.  變更 **[名稱]** 資料行的定序，然後儲存資料表。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

