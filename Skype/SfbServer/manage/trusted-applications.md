---
title: 管理信任的應用程式
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 信任的應用程式是以 Microsoft 整合通訊 Managed API (UCMA) 3.0 核心 SDK 為基礎的應用程式，該應用程式是由商務用 Skype Server 所信任。
ms.openlocfilehash: 2025e8cf51852caeaebd96273c918764c58ce146d87bd4673854514c78b0794f
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848468"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>在商務用 Skype Server 中管理信任的應用程式

*信任的應用程式* 是以 Microsoft 整合通訊 Managed API (UCMA) 3.0 核心 SDK 為基礎的應用程式，該應用程式是由商務用 Skype Server 所信任。 如需 UCMA 應用程式的詳細資訊，請參閱中的「整合通訊 Managed API 3.0 核心 SDK 檔」 https://go.microsoft.com/fwlink/p/?linkId=210320 。

您應以 RTCUniversalServerAdmins 及 Domain Admins 群組成員的身分登入，才能在加入或移除伺服器角色時，成功地發行、啟用或停用拓撲。 

您可以使用本文來瞭解如何設定新的信任應用程式伺服器、查看信任的應用程式清單，以及查看信任的應用程式資訊。 

## <a name="configure-a-new-trusted-application-server"></a>設定新的信任應用程式伺服器

1.  以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。

2.  啟動拓撲產生器：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype Server**]，然後按一下 [**商務用 Skype Server 拓撲** 產生器]。

3.  選取 **[從現有部署下載拓撲]**，然後按一下 **[確定]**。

4.  在 [ **另存拓撲** ] 對話方塊中，按一下您要使用的拓撲產生器檔案，然後按一下 [ **儲存**]。

5.  在左窗格中，以滑鼠右鍵按一下 [ **信任的應用程式伺服器**]，然後按一下 [ **新增信任的應用程式集** 區]。

6.  輸入信任的應用程式集區的 [集區 FQDN]，選擇要讓它成為單一伺服器或多部伺服器，然後按 [下一步]。

7.  在 [**選取下一個躍點]** 頁面上，從清單中選取商務用 Skype Server 前端集區。

8.  按一下 **[完成]**。

9.  選取上方節點 **商務用 Skype Server**，然後從 [**動作**] 功能表中，按一下 [**發行拓撲**]。
    
    **信任的應用程式集** 區應已成功建立，並與正確的前端集區相關聯。


## <a name="view-a-list-of-trusted-applications"></a>查看信任的應用程式清單

您可以使用商務用 Skype Server 控制台，以查看您在商務用 Skype Server 環境中部署的受信任應用程式清單。 信任的應用程式是以 Microsoft 整合通訊 Managed API (UCMA) 3.0 核心 SDK 為基礎的應用程式，該應用程式是由商務用 Skype Server 所信任。 此信任關係摘要如下清單所示：

  - 信任的應用程式不會受到商務用 Skype Server 的驗證的挑戰。

  - 受信任的應用程式不會受到 SIP 交易、連線或透過網際網路通訊協定 (VoIP) 呼叫的商務用 Skype Server 所限制。

  - 信任的應用程式可以模仿任何使用者，並且可以加入會議，而不會出現在名冊中。

  - 信任的應用程式具有高可用性和彈性。

在 [商務用 Skype Server 控制台] 中，您可以看到應用程式的名稱、執行所在的集區，以及使用的埠。


### <a name="to-view-a-list-of-trusted-applications"></a>若要查看信任的應用程式清單

1.  從指派給 CsServerAdministrator、CsAdministrator、CsHelpDesk 或 CsViewOnlyAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。 如需商務用 Skype Server 中所提供的預先定義管理角色的詳細資訊，請參閱以[角色為基礎的存取控制 (RBAC) ](../plan-your-deployment/security/role-based-access-control-rbac.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。

3.  在左導覽列中，按一下 [ **拓撲**]，然後按一下 [ **信任的應用程式**]。

4.  在 [ **信任的應用程式** ] 頁面上，按一下欄標題以排序應用程式（如有必要）。


## <a name="view-trusted-application-information"></a>查看信任的應用程式資訊

您可以使用 Windows PowerShell 和 **Get-CsTrustedApplication** 指令程式，查看您信任之應用程式的相關資訊。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話執行此 Cmdlet。 


### <a name="to-view-trusted-applications"></a>檢視信任的應用程式

若要查看您的所有信任的應用程式，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 enter：
    
   **Get-CsConferenceDisclaimer**
    
   對於各個信任的應用程式，這個命令將傳回類似下列的資訊：
    
   Identity： CN = {5dedf4b0-a590-49b3-80cf-f16f914bbef9}，CN = Application Contacts，CN = RTC Service，CN=Services，CN=Configuration，DC = litware，DC=com<br/>
   RegistrarPool：487279971<br/>
   HomeServer： CN = Lc Services，CN=Microsoft，CN = co1：2，CN = Pool，CN = RTC Service，CN=Services，CN=Configuration，DC = litware，DC=com OwnerUrn： urn： application：<br/>
   SipAddress： sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com<br/>
   DisplayName：<br/>
   DisplayNumber：<br/>
   LineURI<br/>
   PrimaryLanguage：0<br/>
   SecondaryLanguages： {}<br/>
   EnterpriseVoiceEnabled： True<br/>
   ExUmEnabled： False<br/>
   Enabled： True<br/>
    
   如需詳細資訊，請參閱＜[Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication)＞。