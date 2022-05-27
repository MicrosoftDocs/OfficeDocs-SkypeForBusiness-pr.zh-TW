---
title: 管理信任的應用程式
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 受信任的應用程式是以 Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK 為基礎的應用程式，受到商務用 Skype Server信任。
ms.openlocfilehash: 909ade1fbb44410d6b2acb695b8111e43d766e50
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674535"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>在 商務用 Skype Server 中管理信任的應用程式

*受信任的應用程式* 是以 Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK 為基礎的應用程式，受到商務用 Skype Server信任。 For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at https://go.microsoft.com/fwlink/p/?linkId=210320.

您應以 RTCUniversalServerAdmins 及 Domain Admins 群組成員的身分登入，才能在加入或移除伺服器角色時，成功地發行、啟用或停用拓撲。 

使用本文瞭解如何設定新的受信任應用程式伺服器、檢視信任的應用程式清單，以及檢視受信任的應用程式資訊。 

## <a name="configure-a-new-trusted-application-server"></a>設定新的受信任應用程式伺服器

1.  以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。

2.  啟動拓撲產生器：依序按一下 [**開始**]、[**所有程式]**、**[商務用 Skype Server**]，然後按一下 **[商務用 Skype Server拓撲產生器]**。

3.  選取 **[從現有部署下載拓撲]**，然後按一下 **[確定]**。

4.  在 [ **另存拓撲]** 對話方塊中，按一下您要使用的拓撲產生器檔案，然後按一下 [ **儲存]**。

5.  在左窗格中，以滑鼠右鍵按一下 [ **信任的應用程式伺服器]**，然後按一下 [ **新增信任的應用程式集區]**。

6.  輸入信任的應用程式集區的 [集區 FQDN]，選擇要讓它成為單一伺服器或多部伺服器，然後按 [下一步]。

7.  在 [**選取下一個躍** 點] 頁面上，從清單中選取商務用 Skype Server前端集區。

8.  按一下 **[完成]**。

9.  選取頂端節 **點商務用 Skype Server**，然後從 [**動作**] 功能表按一下 [**發佈拓撲]**。
    
    應該已成功建立 **信任的應用程式集區** ，並與正確的前端集區相關聯。


## <a name="view-a-list-of-trusted-applications"></a>檢視受信任應用程式的清單

您可以使用商務用 Skype Server 主控台來檢視您已在商務用 Skype Server環境中部署的信任應用程式清單。 受信任的應用程式是以 Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK 為基礎的應用程式，受到商務用 Skype Server信任。 下列清單摘要說明此信任關係：

  - 受信任的應用程式不會受到商務用 Skype Server的驗證挑戰。

  - 受信任的應用程式不會受到 SIP 交易、連線或透過網際網路通訊協定傳出語音的商務用 Skype Server節流， (VoIP) 呼叫。

  - 信任的應用程式可以模擬任何使用者，而且可以加入會議，而不會出現在名冊中。

  - 受信任的應用程式具有高可用性和復原性。

在商務用 Skype Server 主控台中，您可以看到應用程式的名稱、其執行所在的集區，以及它們使用的埠。


### <a name="to-view-a-list-of-trusted-applications"></a>檢視受信任應用程式的清單

1.  從指派給 CsServerAdministrator、CsAdministrator、CsHelpDesk 或 CsViewOnlyAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。 如需商務用 Skype Server中可用之預先定義系統管理角色的詳細資訊，請參閱[角色型存取控制 (RBAC) ](../plan-your-deployment/security/role-based-access-control-rbac.md)。

2.  開啟瀏覽器視窗，然後輸入管理員 URL 以開啟商務用 Skype Server 主控台。

3.  在左側導覽列中，按一下 [ **拓撲]**，然後按一下 [ **信任的應用程式]**。

4.  在 [ **信任的應用程式** ] 頁面上，視需要按一下資料行標題來排序應用程式。


## <a name="view-trusted-application-information"></a>檢視信任的應用程式資訊

您可以使用 Windows PowerShell 和 **Get-CsTrustedApplication** Cmdlet 來檢視受信任應用程式的相關資訊。 此 Cmdlet 可以從商務用 Skype Server管理命令介面或從Windows PowerShell的遠端會話執行。 


### <a name="to-view-trusted-applications"></a>檢視信任的應用程式

若要檢視所有受信任的應用程式，請在 [商務用 Skype Server 管理命令介面] 中輸入下列命令，然後按 ENTER：
    
   **Get-CsConferenceDisclaimer**
    
   對於各個信任的應用程式，這個命令將傳回類似下列的資訊：
    
   身分識別：CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9}，CN=Application Contacts，CN=RTC Service，CN=Services，CN=Configuration，DC=litware，DC=com<br/>
   RegistrarPool ：487279971<br/>
   HomeServer ： CN=Lc Services，CN=Microsoft，CN=co1：2，CN=Pools，CN=RTC Service，CN=Services，CN=Configuration，DC=litware，DC=com OwnerUrn ： urn：application：helpdesk<br/>
   SipAddress ：sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com<br/>
   DisplayName ：<br/>
   DisplayNumber ：<br/>
   LineURI：<br/>
   PrimaryLanguage ： 0<br/>
   SecondaryLanguages ： {}<br/>
   EnterpriseVoiceEnabled ：True<br/>
   ExUmEnabled ： False<br/>
   已啟用：True<br/>
    
   如需詳細資訊，請參閱＜[Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication)＞。