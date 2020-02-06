---
title: 管理受信任的應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 受信任的應用程式是以 Microsoft 整合通訊 Managed API （UCMA）3.0 核心 SDK （受商務用 Skype Server 信任）為基礎的應用程式。
ms.openlocfilehash: b2a257ad197d573beccb187ef49e41b3864c1a58
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817074"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>在商務用 Skype Server 中管理受信任的應用程式

*受信任的應用程式*是以 Microsoft 整合通訊 Managed API （UCMA）3.0 核心 SDK （受商務用 Skype Server 信任）為基礎的應用程式。 如需有關 UCMA 應用程式的詳細資訊，請參閱「統一通訊管理的http://go.microsoft.com/fwlink/p/?linkId=210320API 3.0 核心 SDK 檔」。

若要在新增或移除伺服器角色時成功發佈、啟用或停用拓撲，您應該以 RTCUniversalServerAdmins 和網域系統管理員群組成員的使用者身分登入。 

您可以在本文中瞭解如何設定新的受信任應用程式伺服器、查看信任的應用程式清單，以及查看受信任的應用程式資訊。 

## <a name="configure-a-new-trusted-application-server"></a>設定新的信任應用程式伺服器

1.  登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。

2.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype server**]，然後按一下 [**商務用 skype server 拓撲**建立器]。

3.  選取 [**從現有部署下載拓朴**]，然後按一下 **[確定]**。

4.  在 [**另存拓朴為**] 對話方塊中，按一下您要使用的拓撲產生器檔案，然後按一下 [**儲存**]。

5.  在左窗格中，以滑鼠右鍵按一下 [**信任的應用程式伺服器**]，然後按一下 [**新增信任的應用程式池**]。

6.  輸入受信任的應用程式池的 [**池 FQDN** ]，選取它是否為單一伺服器或多重伺服器，然後按 **[下一步]**。

7.  在 [**選取下一個躍點]** 頁面上的清單中，選取 [商務用 Skype Server 前端] 池。

8.  按一下 **[完成]**。

9.  選取最上層**的商務用 Skype Server**，然後在 [**動作**] 功能表中，按一下 [**發佈拓撲**]。
    
    **受信任的應用程式池**應該已成功建立，且與正確的 [前端] 池相關聯。


## <a name="view-a-list-of-trusted-applications"></a>查看信任的應用程式清單

您可以使用商務用 Skype Server 的 [控制台] 來查看您在商務用 Skype Server 環境中部署之受信任的應用程式清單。 受信任的應用程式是以 Microsoft 整合通訊 Managed API （UCMA）3.0 核心 SDK （受商務用 Skype Server 信任）為基礎的應用程式。 下列清單將摘要列出這項信任關係：

  - 商務用 Skype Server 不會對受信任的應用程式進行驗證。

  - 受信任的應用程式不會受到 SIP 交易、連線或網際網路通訊協定（VoIP）通話的商務用 Skype 伺服器的限制。

  - 受信任的應用程式可以模仿任何使用者，而且無需出現在 rosters 中，即可加入會議。

  - 受信任的應用程式高度可用且具有彈性。

在商務用 Skype Server 的 [控制台] 中，您可以看到應用程式名稱、其執行所在的池中，以及它們所使用的埠。


### <a name="to-view-a-list-of-trusted-applications"></a>若要查看受信任的應用程式清單

1.  從指派給 CsServerAdministrator、CsAdministrator、CsHelpDesk 或 CsViewOnlyAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。 如需有關商務用 Skype Server 中可用的預先定義管理角色的詳細資訊，請參閱以[角色為基礎的存取控制（RBAC）](../plan-your-deployment/security/role-based-access-control-rbac.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。

3.  在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**信任的應用程式**]。

4.  如有需要，請在 [**受信任的應用程式**] 頁面上，按一下欄標題來排序應用程式。


## <a name="view-trusted-application-information"></a>查看受信任的應用程式資訊

您可以使用 Windows PowerShell 和**CsTrustedApplication** Cmdlet 來查看您信任之應用程式的相關資訊。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 


### <a name="to-view-trusted-applications"></a>若要查看受信任的應用程式

若要查看所有受信任的應用程式，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER：
    
        Get-CsConferenceDisclaimer
    
   這個命令會針對每個受信任的應用程式傳回類似下列的資訊：
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   如需詳細資訊，請參閱[CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication)。
