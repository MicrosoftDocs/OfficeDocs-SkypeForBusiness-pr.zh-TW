---
title: 在商務用 Skype Server 中部署 SRS v1 管理網頁入口網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: 商務用 Skype Server Skype 室系統 v1 (SRS v1, 先前稱為 Lync 室系統) 系統管理網頁入口網站是一種網路入口網站, 組織可以用來維護其 Skype 會議室系統會議室。 系統管理員可以使用 SRS v1 管理網頁入口網站來監視裝置的健康情況, 例如, 透過監視音訊/視頻裝置。 有了這個入口網站, 管理員就可以遠端收集診斷資訊來監控會議室的健康情況。
ms.openlocfilehash: bf18cefbdaa5beeaef63d16b5447cce2969fc147
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234172"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>在商務用 Skype Server 中部署 SRS v1 管理網頁入口網站

商務用 Skype Server Skype 室系統 v1 (SRS v1, 先前稱為 Lync 室系統) 系統管理網頁入口網站是一種網路入口網站, 組織可以用來維護其 Skype 會議室系統會議室。 系統管理員可以使用 SRS v1 管理網頁入口網站來監視裝置的健康情況, 例如, 透過監視音訊/視頻裝置。 有了這個入口網站, 管理員就可以遠端收集診斷資訊來監控會議室的健康情況。

若要使用此功能, 必須在每個商務用 Skype Server 前端伺服器上部署 SRS v1 系統管理網頁入口網站。 本指南提供系統管理員如何安裝和設定 SRS 管理網頁入口網站的指示。 它適用于瞭解商務用 Skype Server 管理的管理員, 以及誰有管理員使用者許可權來修改商務用 Skype Server 拓撲。

在伺服器上部署 SRS v1 管理網頁入口網站之後, 系統管理員可以從自己的電腦或膝上型電腦登入該網站, 以檢查狀態 SRS v1 裝置。

> [!IMPORTANT]
> 下載[適用于商務用 Skype Server 2015 的 Microsoft Skype 會議室系統 V1 管理網頁入口網站](https://www.microsoft.com/en-us/download/details.aspx?id=46906)。

本主題內容如下:

- [針對 SRS v1 管理網頁入口網站設定您的環境](room-system-v1-administrative-web-portal.md#Config_Env)

- [安裝 SRS v1 管理網頁入口網站](room-system-v1-administrative-web-portal.md#Install_SRS)

- [使用 SRS 管理網頁入口網站](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>針對 SRS v1 管理網頁入口網站設定您的環境
<a name="Config_Env"> </a>

若要使用 SRS v1 管理網頁入口網站, 您將需要安裝或設定下列先決條件。

> [!IMPORTANT]
> 如果伺服器已設定 Kerberos 和 NTLM 驗證, 而 SRS 是在未加入網域的電腦上執行, Kerberos 驗證將會失敗, 而且使用者在管理入口網站中將不會看到 SRS 的狀態。 若要解決此問題, 請使用 NTLM 驗證或 NTLM 與 TLS DSK 驗證 (沒有 Kerberos) 來設定伺服器, 或將 SRS 電腦加入網域。

1. 在商務用 Skype Server 拓朴中安裝商務用 Skype Server 累計更新。

    若要取得更新或查看其隨附的內容, 請參閱[商務用 Skype Server 2015 更新](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。

2. 建立啟用 SIP 的 Active Directory 使用者。

    SRS v1 管理網頁入口網站使用這些認證來查詢商務用 Skype Server 的資訊。 在給定範例中的使用者名稱為 LRSApp。

3. 使用 [名稱 LRSSupportAdminGroup] 建立 Active Directory 安全性群組。

    建立群組範圍為全域且群組類型為安全性的群組。 加入到這個群組的 SIP 啟用的使用者, 都會獲授權查看聊天室清單並執行某些命令, 例如收集記錄。

4. 使用 [名稱 LRSFullAccessAdminGroup] 建立 Active Directory 安全性群組。

    建立群組範圍為全域和群組類型做為安全性的群組。加入此群組的 SIP 啟用的使用者已獲授權使用單一 Skype 聊天室上的所有系統管理入口網站功能。 若要包含對 Skype 會議室大量管理的支援, 請參閱步驟5。

     ![具有安全性群組角色之管理員群組的清單](../../media/LRS_LRSFullAccessAdminGroup.png)

5. 使用 [名稱 LRSPowerUserAdminsGroup] 建立 Active Directory 安全性群組。

    建立群組範圍為全域且群組類型為安全性的群組。 已授權已加入此群組的 SIP 使用者可使用所有系統管理入口網站功能, 包括大量管理商務用 Skype 會議室。

6. 將 LRSFullAccessAdminGroup 新增為 LRSSupportAdminGroup 的成員。

     ![[LRSSupportAdminGroup 內容成員] 頁面](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. 使用 [名稱 LRSSupport] 建立啟用 SIP 的 Active Directory 使用者。 將此使用者新增至 LRSSupportAdminGroup。

     ![[LRSSupportAdminGroup 內容成員] 頁面](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. [針對 Visual Studio 2010 sp1 及 Visual Web 開發人員 2010 SP1, 安裝 ASP.NET MVC 4](https://go.microsoft.com/fwlink/p/?LinkId=323967)。

## <a name="install-the-srs-v1-administrative-web-portal"></a>安裝 SRS v1 管理網頁入口網站
<a name="Install_SRS"> </a>

下載[適用于商務用 Skype Server 2015 的 Microsoft Skype 會議室系統 V1 管理網頁入口網站](https://www.microsoft.com/en-us/download/details.aspx?id=46906)。

若要安裝 SRS v1 管理網頁入口網站, 請使用下列步驟。

1. 在商務用 Skype Server Management 命令介面中執行下列 Cmdlet, 以設定受信任的應用程式埠:

   ```
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. 若要安裝會議室入口網站, 請下載**MeetingRoomPortalInstaller** , 然後以系統管理員身分執行。

3. 從下列位置開啟 Web.config 檔案:

    商務用 Files%\Skype for Business Server 2015 \ Web Components\Meeting 聊天室 Portal\Int\Handler\

4. 在 web.config 檔案中, 將 PortalUserName 變更為在步驟2中建立的使用者名稱, 在「[設定您的 SRS V1 管理網頁入口網站](room-system-v1-administrative-web-portal.md#Config_Env)」區段 (步驟中的建議名稱是 LRSApp) 中。

    ```
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. 由於 SRS v1 管理入口網站是受信任的應用程式, 因此您不需要在入口網站設定中提供密碼。 如果此使用者使用的註冊機構並非是本機註冊機構, 您必須在 Web.config 檔案中加入下列一行, 以指定其註冊機構:

   ```
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. 如果使用的埠不是 5061, 請在 web.config 檔案中新增下列行:

   ```
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>驗證 SRS 管理網頁入口網站的安裝

若要驗證 SRS v1 管理網頁入口網站的安裝, 請執行下列動作:

1. 在前端伺服器上, 流覽至下列 URL:

    HTTPs://\<fe-伺服器\>/lrs

    您不應該看到任何錯誤, 如下圖所示:

     ![[Lync Room System 管理入口網站登入] 畫面](../../media/LRS_AdminPortalSignIn.png)

2. 如果您沒有看到任何錯誤, 請嘗試從拓撲中的任何其他電腦存取下列 URL:

    HTTPs://\<fe-伺服器\>/lrs

    若要存取頁面, 您需要新增 DNS 記錄, 如「[自動用戶端登入所需的 DNS 記錄](https://go.microsoft.com/fwlink/p/?LinkId=318056)」中所述。

## <a name="use-the-srs-administrative-web-portal"></a>使用 SRS 管理網頁入口網站
<a name="Use_Portal"> </a>

在伺服器上部署 SRS 之後, 您可以從瀏覽器登入 SRS v1 管理網頁入口網站, 以檢查所有 SRS 聊天室的狀態。

### <a name="sign-in"></a>登錄

1. 流覽至下列 URL:

    HTTPs://\<fe-伺服器\>/lrs

2. 輸入 LRSSupport 帳戶的認證, 或是新增至 LRSSupportAdminGroup 安全性群組的帳戶。

![[Lync Room System 管理入口網站登入] 畫面](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>SRS 系統管理網頁入口網站摘要頁面

[摘要] 頁面提供伺服器上部署之所有 SRS 聊天室的下列資訊:

- **標記**管理員提供給聊天室的自訂名稱。 您可以按一下房間名稱, 在入口網站中設定標籤。

- **健康情況**聊天室的健康情況狀態是衍生自聊天室的匯總健康情況, 這會顯示在 [會議室設定] 頁面的 [健康情況] 區段底下。

- **下次會議**排程下次會議的日期和時間。

- **SRS 版本、製造商、型號**這些值是在 SRS 中預先設定。 視製造商而定, 這些欄位可能會保留空白。

- **上次**重新整理顯示最後一次重新整理網頁的時間。

![Lync Room System 管理入口網站摘要檢視](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> 如果您是 [LRSPowerUserAdminsGroup] 安全性群組的一部分, 您就只會看到 [大量管理] 功能表。

### <a name="srs-room-information"></a>SRS 聊天室資訊

入口網站的 [聊天室資訊] 區段可讓您查看和設定個別的 SRS 聊天室。 它包含四個區段: 設定、詳細資料、記錄和健康情況。

#### <a name="settings"></a>設置

在 [設定] 區段中, 您可以設定聊天室的密碼、房間標籤及預設音量等級。 如果您設定這些設定, 變更只會在您重新開機 SRS 主控台後進行複製。 您只會看到使用版本15.12 和更新版本之 SRS 裝置的 [系統更新] 設定。

![Lync Room System 管理入口網站會議室設定](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>詳細資料

[詳細資料] 區段提供 SRS 聊天室設定的唯讀摘要, 包括: 上次重新整理的時間;下次會議;上次更新、維護和校準;預設喇叭、麥克風和鈴聲設定;新版SIP URI;螢幕數目及每個畫面的詳細資料;狀態和活動。

![Lync Room System 管理入口網站詳細資料檢視](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>疑難排解

疑難排解一節可用來遠端收集記錄, 並將它們儲存到指定的位置。 您也可以重新開機 SRS 主控台 (SRS 使用者介面), 或重新開機整個系統。 若要收集記錄, 請以指定的格式提供資料夾路徑, 並確認資料夾擁有對 SRS 電腦帳戶的寫入權限。 如果記錄大小太大, 可能需要最多5分鐘的時間來完成收集記錄。 重新整理頁面會提供最新狀態。

#### <a name="health"></a>運行

[健康情況] 區段會顯示商務用 Skype Server 連線、音訊裝置、視頻裝置、復原狀態及螢幕裝置的健康情況的視覺指示。

![Lync Room System 管理入口網站會議室健康情況](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>有關系統管理網頁入口網站的其他注意事項

> [!NOTE]
>  只有在重新開機 SRS 系統之後, 才會套用設定變更。 > 如果 LRSApp 帳戶密碼到期, 您將無法看到聊天室的狀態。 設定 LRSAppuser 帳戶密碼, 使其永不過期, 或者請務必在接近到期時更新密碼。 > SRS 系統管理網頁入口網站僅支援內部部署部署。

### <a name="bulk-management"></a>大量管理

SRS 會議室的大量管理是專為高級 IT 系統管理員設計的功能, 可簡化其工作流程, 並讓他們使用節省時間的工具, 以大量方式遠端系統管理多個會議室。

若要查看這項功能, 必須將使用者設為特殊安全性群組的成員 ( **LRSPowerUserAdminsGroup**)。

對於大量管理, 您可以選取的 SRS 會議室數沒有限制。 不過, 您一次只能執行一個大量的管理作業。

若要執行大量管理作業, 請選取您要監視的聊天室, 然後按一下 [大量管理] 功能表。

### <a name="frequently-asked-questions"></a>常見問題

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>為什麼我無法登入系統管理網頁入口網站？

當您開啟https://localhost/lrs時, 您可以看到 [登入] 頁面, 但是當您輸入認證時, 就無法登入。 在這種情況下, 您https://FQDNofFEserver/SRS必須開啟, 才能登入管理網頁入口網站。

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>為什麼在管理網頁入口網站中看不到 SRS v1？

- 請確定您在部署中擁有 SRS 帳戶, 並根據 SRS 管理網頁入口網站部署建議來建立它們。 在商務用 Skype 伺服器上, 確定已使用 Enable-CsMeetingRoom, 而不是 Enable-Move-csuser 來提供 SRS 帳戶。

- 如果您已建立 SRS 帳戶, 但在管理網頁入口網站中看不到帳戶, 請使用已選取 [ **MeetingPortal** ] 元件的商務用 Skype server 記錄工具收集伺服器記錄, 然後將其傳送給您的 SRS 支援連絡人。

- 如果您已建立 SRS 帳戶, 但在管理網頁入口網站中看不到帳戶, 請使用 Fiddler 收集用戶端記錄, 也可以從瀏覽器開發工具複製主機日誌, 然後將其傳送給您的 SRS 支援連絡人。 您也可以修改 web.config 中的 [追蹤層級] 值, 以取得更詳細的記錄。

  ```
  <system.diagnostics>
    <switches>
      <!--
      This switch controls logging message levels. 0 implies
      logging is turned off. 1 implies only errors are logged,
      2 implies errors &amp; warnings. 4 is the most detailed.
      -->
      <add name="TraceLevelSwitch" value="3" />
    </switches>
  </system.diagnostics>
  ```

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>為什麼在管理網頁入口網站中看不到 SRS 的狀態？

- 確認 LRSApp 使用者帳戶已啟用 SIP。

- 如果您仍有問題, 請從 D:\Tracing\LRSAdminLogs\,收集 SRS 系統中的**Trace .log**檔案, 然後將其傳送給您的 SRS 支援連絡人。

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>為什麼在管理網頁入口網站中看不到 SRS 的大量管理功能表？

確認 LRSApp 使用者帳戶已啟用 SIP, 且是 LRSPowerUserAdminsGroup 安全性群組的一部分。

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>SRS v1 管理網頁入口網站與 Microsoft 團隊聊天室搭配使用嗎？

不。


