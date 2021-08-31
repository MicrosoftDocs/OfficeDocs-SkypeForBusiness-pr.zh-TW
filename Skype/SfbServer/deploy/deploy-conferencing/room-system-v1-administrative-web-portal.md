---
title: 在商務用 Skype Server 中部署 SRS v1 管理網頁入口網站
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: 商務用 Skype Server Skype 會議室 Systems (SRS v1 （以前稱為 Lync 會議室系統) 管理網頁入口網站）是一個網頁入口網站，組織可以用來維護其 Skype 的會議室系統會議室。 系統管理員可以使用 SRS v1 管理網頁入口網站來監視裝置健康情況，例如，監控音訊/視頻裝置。 使用此入口網站，系統管理員可以遠端收集診斷資訊以監視會議室健康情況。
ms.openlocfilehash: 0b52657d33b4da97266a635b53459ed21fd4a944
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729112"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>在商務用 Skype Server 中部署 SRS v1 管理網頁入口網站

商務用 Skype Server Skype 會議室 Systems (SRS v1 （以前稱為 Lync 會議室系統) 管理網頁入口網站）是一個網頁入口網站，組織可以用來維護其 Skype 的會議室系統會議室。 系統管理員可以使用 SRS v1 管理網頁入口網站來監視裝置健康情況，例如，監控音訊/視頻裝置。 使用此入口網站，系統管理員可以遠端收集診斷資訊以監視會議室健康情況。

若要使用此功能，您必須在每一部商務用 Skype Server 前端伺服器上部署 SRS v1 管理網頁入口網站。 本指南提供系統管理員如何安裝和設定 SRS 管理網頁入口網站的指示。 其適用于具備商務用 Skype Server 管理功能的系統管理員，以及具備修改商務用 Skype Server 拓撲的管理員使用者權限。

在伺服器上部署 SRS v1 系統管理 Web 入口網站後，系統管理員可以從自己的電腦或膝上型電腦登入網站，以檢查狀態 SRS v1 裝置。

> [!IMPORTANT]
> 下載[適用于商務用 Skype Server 2015 的 Microsoft Skype 機房系統 v1 管理網頁入口網站](https://www.microsoft.com/download/details.aspx?id=46906)。

本主題內容：

- [設定 SRS v1 系統管理 Web 入口網站的環境](room-system-v1-administrative-web-portal.md#Config_Env)

- [安裝 SRS v1 系統管理 Web 入口網站](room-system-v1-administrative-web-portal.md#Install_SRS)

- [使用 SRS 系統管理 Web 入口網站](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>設定 SRS v1 系統管理 Web 入口網站的環境
<a name="Config_Env"> </a>

若要使用 SRS v1 管理網頁入口網站，您必須安裝或設定下列必要條件。

> [!IMPORTANT]
> 如果伺服器設定了 Kerberos 和 NTLM 驗證，而 SRS 是在未加入網域的電腦上執行，則 Kerberos 驗證會失敗，且使用者將不會在系統管理入口網站看到 SRS 的狀態。 若要解決此問題，請使用沒有 Kerberos) 的 ntlm 和 TLS DSK 驗證 (來設定伺服器，或將 SRS 電腦加入網域。

1. 在商務用 Skype Server 拓撲中安裝商務用 Skype Server 累計更新。

    若要取得更新或查看其隨附的內容，請參閱[商務用 Skype Server 2015 的更新](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。

2. 建立 SIP-enabled Active Directory 使用者。

    SRS v1 系統管理 Web 入口網站會使用這些認證，從商務用 Skype Server 查詢資訊。 指定範例中的使用者名稱是 LRSApp。

3. 使用 name LRSSupportAdminGroup 建立 Active Directory 安全性群組。

    以「全域」和「群組」類型為安全性的群組範圍建立群組。 新增至此群組的 SIP 啟用使用者可查看聊天室清單，並執行某些命令，例如收集記錄檔。

4. 使用名稱 LRSFullAccessAdminGroup 建立 Active Directory 安全性群組。

    以「全域」和「群組」類型為安全性的群組範圍建立群組。加入至此群組的 SIP 啟用使用者，可在單一 Skype 會議室上使用所有系統管理員入口網站功能。 若要包含對 Skype 會議室大量管理的支援，請參閱步驟5。

     ![具有安全性群組角色的系統管理員群組清單。](../../media/LRS_LRSFullAccessAdminGroup.png)

5. 使用名稱 LRSPowerUserAdminsGroup 建立 Active Directory 安全性群組。

    以「全域」和「群組」類型為安全性的群組範圍建立群組。 加入至此群組的 SIP 啟用使用者，都有權使用所有系統管理員入口網站功能，包括商務用 Skype 會議室的大量管理。

6. 將 LRSFullAccessAdminGroup 新增為 LRSSupportAdminGroup 的成員。

     ![LRSSupportAdminGroup 屬性成員] 頁面。](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. 使用名稱 LRSSupport 建立啟用 SIP 的 Active Directory 使用者。 將此使用者新增至 LRSSupportAdminGroup。

     ![LRSSupportAdminGroup 屬性成員] 頁面。](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. [針對 Visual Studio 2010 SP1 和 Visual Web Developer 2010 SP1 安裝 ASP.NET MVC 4](https://go.microsoft.com/fwlink/p/?LinkId=323967)。

## <a name="install-the-srs-v1-administrative-web-portal"></a>安裝 SRS v1 系統管理 Web 入口網站
<a name="Install_SRS"> </a>

下載[適用于商務用 Skype Server 2015 的 Microsoft Skype 機房系統 v1 管理網頁入口網站](https://www.microsoft.com/download/details.aspx?id=46906)。

若要安裝 SRS v1 系統管理 Web 入口網站，請使用下列步驟。

1. 在商務用 Skype Server 管理命令介面中執行下列 Cmdlet，以設定信任的應用程式埠：

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. 若要安裝會議室入口網站，請下載 **MeetingRoomPortalInstaller.msi** ，然後以系統管理員身分執行。

3. 從下列位置開啟 Web.config 檔案：

    % Program Files% \ 商務用 Skype Server 2015 \ Web 元件 \ 會議室 Portal\Int\Handler\

4. 在 Web.Config 檔案中，將 PortalUserName 變更為在步驟2中建立的使用者名稱，並在 [[設定您的 SRS v1 系統管理 Web 入口網站](room-system-v1-administrative-web-portal.md#Config_Env)」區段下， (步驟中的建議名稱是 LRSApp) ：

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. 由於 SRS v1 管理入口網站是受信任的應用程式，因此您不需要在入口網站設定中提供密碼。 若此使用者使用不同的註冊機構，您必須在 Web.Config 檔案中新增下列一行，以指定其註冊機構：

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. 如果使用的埠不是5061，請在 Web.Config 檔案中新增下行：

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>驗證 SRS 管理網頁入口網站的安裝

若要驗證 SRS v1 系統管理 Web 入口網站的安裝，請執行下列操作：

1. 在前端伺服器上，流覽至下列 URL:

    HTTPs:// \<fe-server\> /lrs

    您不應該看到任何錯誤，如下圖所示：

     ![Lync 會議室系統管理入口網站登入畫面。](../../media/LRS_AdminPortalSignIn.png)

2. 如果您未看到任何錯誤，請嘗試從拓撲中的任何其他電腦存取下列 URL：

    HTTPs:// \<fe-server\> /lrs

    若要存取此頁面，您必須以「[自動用戶端 Sign-In 所需的 Dns 記錄](/previous-versions/office/communications-server/bb663700(v=office.12))」所述，新增 DNS 記錄。

## <a name="use-the-srs-administrative-web-portal"></a>使用 SRS 系統管理 Web 入口網站
<a name="Use_Portal"> </a>

在伺服器上部署 SRS 之後，您可以在瀏覽器中登入 SRS v1 管理網頁入口網站，以檢查所有 SRS 聊天室的狀態。

### <a name="sign-in"></a>登入

1. 流覽至下列 URL:

    HTTPs:// \<fe-server\> /lrs

2. 輸入 LRSSupport 帳戶的認證，或加入 LRSSupportAdminGroup 安全性群組的帳戶。

![Lync 會議室系統管理入口網站登入畫面。](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>SRS 系統管理 Web 入口網站摘要頁面

[摘要] 頁面針對伺服器上部署的所有 SRS 聊天室，提供下列資訊：

- **標記** 管理員提供給會議室的自訂名稱。 您可以在入口網站中，按一下會議室名稱以設定標記。

- **健全狀況** 會議室的健全狀況狀態，它是以會議室的合計健康狀態所組成，它會顯示在會議室設定] 頁面的 [健全狀況] 區段下。

- **下一個會議** 排定下一個會議的日期和時間。

- **SRS 版本、製造商、模型** 這些值是 SRS 中的預置。 視製造商而定，這些欄位可能會保留空白。

- **上次** 重新整理顯示上次重新整理網頁的時間。

![Lync 會議室系統管理入口網站摘要視圖。](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> 如果您是 LRSPowerUserAdminsGroup 安全性群組的一部分，您只會看到 [大量管理] 功能表。

### <a name="srs-room-information"></a>SRS 聊天室資訊

入口網站的 [聊天室資訊] 區段可讓您查看及設定個別的 SRS 聊天室。 包含四個區段： [設定]、[詳細資料]、[記錄] 及 [健全]。

#### <a name="settings"></a>設定

在 [設定] 區段中，您可以設定會議室的密碼、會議室標記和預設磁片區層級。 如果您設定這些設定，則只有在您重新開機 SRS 主控台之後才會複製變更。 您只會看到使用版本15.12 和更新版本之 SRS 裝置的系統更新設定。

![Lync 會議室系統管理入口網站聊天室設定。](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>詳細資料

詳細資料區段提供 SRS 聊天室設定的唯讀摘要，包括：上次重新整理的時間;下一個會議;上次更新、維護和校準;預設的喇叭、mic 及鈴聲設定;版本SIP URI;每個畫面的畫面數目及詳細資料;狀態和活動。

![Lync 會議室系統管理員入口網站詳細資料檢視。](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>疑難排解

疑難排解區段可用於遠端收集記錄，並將其儲存到指定的位置。 您也可以重新開機 SRS 主控台 (SRS 使用者介面) 或重新開機整個系統。 若要收集記錄檔，請以指定的格式提供資料夾路徑，並確定資料夾具有 SR 電腦帳戶的寫入權限。 如果記錄檔的大小過大，則最多可能需要5分鐘的時間來收集記錄檔。 重新整理頁面可提供您最新的狀態。

#### <a name="health"></a>健康情況

「健康情況」區段供應商務用 Skype Server connection、音訊裝置、影片裝置、恢復狀態及螢幕裝置狀況的視覺表示。

![Lync 會議室系統管理入口網站室健康情況。](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>關於系統管理 Web 入口網站的其他注意事項

> [!NOTE]
>  只有在 SR 系統重新開機之後，才會套用設定變更。 > 如果 LRSApp 帳戶密碼到期，您將無法看到聊天室的狀態。 設定 LRSAppuser 帳戶密碼，使其永不到期，或務必在密碼即將到期時更新 >。只有內部部署部署才支援 SRS 管理網頁入口網站。

### <a name="bulk-management"></a>大量管理

使用大量管理的 SRS 會議室是專為高級 IT 系統管理員所設計的功能，可簡化其工作流程，並可讓他們使用節省時間的便捷工具，以大量的方式遠端系統管理多個聊天室。

若要看到此功能，使用者必須布建為特殊安全性群組（ **LRSPowerUserAdminsGroup**）的成員。

您可以為大量管理選取的 SRS 聊天室數目沒有任何限制。 不過，您一次只能執行一個大量管理作業。

若要執行大量管理作業，請選取您要監視的聊天室，然後按一下 [大量管理] 功能表上的 [開啟]。

### <a name="frequently-asked-questions"></a>常見問題集

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>為什麼我無法登入管理網頁入口網站？

當您開啟時 https://localhost/lrs ，您可以看到 [登入] 頁面，但是當您輸入您的認證時，您無法登入。 在此情況下，您必須先開啟 https://FQDNofFEserver/SRS 以登入管理 web 入口網站。

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>為什麼我無法看到管理網頁入口網站中的 SRS v1？

- 請確定您的部署中有 SR 帳戶，而且這些帳戶是根據 SRS 管理網頁入口網站部署建議所建立。 請確定已使用商務用 Skype Server 上的 Enable-CsMeetingRoom，而不是啟用 get-csuser 來布建 SRS 帳戶。

- 如果您已建立 sr 帳戶，但在管理 web 入口網站中看不到帳戶，請使用商務用 Skype Server 記錄工具來收集伺服器記錄，並選取 **MeetingPortal** 元件，然後將其傳送至您的 SRS 支援連絡人。

- 如果您已建立 SR 帳戶，但在管理 web 入口網站中看不到這些帳戶，請使用 Fiddler 收集用戶端記錄，並從瀏覽器開發工具複製主控台記錄檔，然後將其傳送至您的 SRS 支援連絡人。 您也可以修改 Web.config 中的追蹤層級值，以取得更詳細的記錄檔。

  ```xml
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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>為什麼我無法在管理網頁入口網站中看到 SRS 的狀態？

- 請確定 LRSApp 的使用者帳戶已 SIP-enabled。

- 如果仍有問題，請從 D:\Tracing\LRSAdminLogs 收集 SRS 系統中的 **Trace .log** 檔案 \, ，然後將它傳送給您的 SRS 支援連絡人。

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>為何在管理網頁入口網站中看不到 SR 的大量管理功能表？

請確定 LRSApp 的使用者帳戶 SIP-enabled，且屬於 LRSPowerUserAdminsGroup 安全性群組的一部分。

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>SRS 的管理網頁入口網站是否與 Microsoft Teams 會議室搭配運作？

否。