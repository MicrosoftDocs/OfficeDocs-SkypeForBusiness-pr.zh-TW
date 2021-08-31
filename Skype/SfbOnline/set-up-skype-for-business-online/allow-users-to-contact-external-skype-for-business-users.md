---
title: 允許使用者連絡外部商務用 Skype 使用者
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: '瞭解如何設定商務用 Skype讓使用者與另一個組織的使用者交談，或讓外部連絡人與使用者交談。 '
ms.openlocfilehash: e98f30718bb44a3ca2e5f48560d7f38552a2ef49
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731112"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>允許使用者連絡外部商務用 Skype 使用者

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
  
在下列時間使用本文中的步驟：
  
- 您擁有公司中不同網域的使用者。 例如，Rob@ContosoEast.com Ann@ContosoWest.com。

- 您希望貴組織中的人員使用 商務用 Skype來與組織外部特定企業中的人員聯繫。

- 您希望世界上任何使用商務用 Skype都能使用您的電子郵件地址尋找並與您聯繫。 如果您和他們在設定中商務用 Skype，這會自動執行。 如果沒有，則他們必須確定其組塊未封鎖您的網域。

## <a name="enable-business-to-business-communications-for-your-users"></a>為使用者啟用企業對商務通訊

<a name="bk_preview"> </a>

您必須擁有[兩個組織](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)Microsoft 365或Office 365管理員許可權，才能進行此通訊。

![顯示標誌圖示Microsoft Teams圖示。](../images/teams-logo-30x30.png) **使用 Teams系統管理中心**
  
1. 使用您的帳戶或Microsoft 365 Office 365帳戶進行登錄。

2. 在系統管理中心，前往系統 **管理中心**  >  **Teams。**

    ![選擇管理員Teams管理員。](../images/MS-Teams-Admin.png)
  
3. 在 Teams **中心**，選擇 **Skype** > **舊版入口網站** 
  ![ 選擇 SfB 舊版入口網站。](../images/SFBlegacy-size65.png)

4. 在 [商務用 Skype 系統管理中心]，選擇 [組織]  >  [外部通訊]。
5. 若要設定與特定公司或其他網域中的使用者進行通訊，請在下拉式方塊中選擇 [僅對允許的網域開啟]。

    或者，如果您想要啟用與全世界所有已開啟此商務用 Skype的通訊，請選擇開啟 ，但封鎖的 **網域** 除外。 這是預設設定。

6. 在 **封鎖或允許的網域** 下，選擇並新增您想要 **+** 允許的功能變數名稱。

7. 請確定另一組織的系統管理員在系統管理中心執行商務用 Skype **步驟**。 例如，在允許 **的網域** 清單中，他們的系統管理員必須輸入您企業網域。

8. 如果您使用的是防火牆Windows，商務用 Skype開啟所需的埠。

    如果貴組織使用不同的防火牆解決方案來限制網路上的電腦無法連接到網際網路，請確保您的用戶端電腦能夠存取下列 Office 365 [URL 和 IP 位址範圍](/microsoftteams/office-365-urls-ip-address-ranges)。 這可能需要將 FQDNs 新增到防火牆或 Proxy 基礎結構組配置的外發允許清單 **\* ：.api.skype.com、.users.storage.live.com** \* *__***和 graph.skype.com。** 若要瞭解如何在防火牆中開啟這些埠的指示，請查看它所提供的檔。

    有關您需要開啟的所有埠清單，請參閱OFFICE 365 URL[和 IP 位址範圍](/microsoftteams/office-365-urls-ip-address-ranges)。

9. 請確定組織的系統管理員也遵循這些步驟。

10. **等候最多 24 小時進行測試**。 當您變更外部通訊設定時，變更最多可能需要 24 小時，才能填入所有資料中心。

![Skype。](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) 您可以允許使用者與使用免費消費者應用程式Skype搜尋和 IM！ 若要深入瞭解，請參閱讓使用者[商務用 Skype新增Skype連絡人](let-skype-for-business-users-add-skype-contacts.md)。
  
## <a name="test-and-troubleshoot"></a>測試和疑難排解

<a name="bk_preview"> </a>

 **在設定企業對商務通訊時，最常見的問題是正確取得Office 365 URL 和 [IP 位址](/microsoftteams/office-365-urls-ip-address-ranges)範圍。**
  
若要測試您的設定，您需要在公司防火牆商務用 Skype的連絡人。
  
1. 變更外部通訊設定之後，請等候 **最多 24 小時進行測試**。

2. 在 商務用 Skype中，在 商務用 Skype中搜尋您的連絡人，然後傳送聊天要求。

    如果您收到由於公司政策而無法送出的郵件，您必須仔細檢查您的 URL 和 IP 位址Office 365 URL[和 IP 位址範圍](/microsoftteams/office-365-urls-ip-address-ranges)。

3. 要求您的商務用 Skype聯絡人傳送聊天邀請。 如果您沒有收到其要求，就表示您的防火牆設定有問題 (假設他們已確認其防火牆設定正確)。

4. 另一個測試問題是否出在防火牆上的方法，就是前往不在防火牆後面的 Wifi 位置，例如咖啡店。 您可以使用 商務用 Skype傳送要求給聯絡人聊天。 如果郵件經過該區，但在您工作時卻無法傳遞，那麼您就會知道問題出在防火牆上。

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>如何尋找其他人，以及如何在與另一個企業聯繫時找到他們

<a name="bk_preview"> </a>

啟用與其他使用者的外部通訊商務用 Skype，您的使用者可以搜尋其商務用 Skype使用者的名稱來尋找已建立聯盟的使用者。 例如，Rob@contoso.com。 接著，他們將需要將人員新增到連絡人清單中。
  
![若要在聯合企業中尋找使用者，您必須搜尋其電子郵件地址 (這通常也是他們) 。](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>提示與聯盟企業設定通訊

<a name="bk_preview"> </a>

- 若要設定 2015 商務用 Skype與 商務用 Skype之間的聯合，請參閱這篇文章：設定與 商務用 Skype[連線的聯盟](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)。

- 若要設定 Lync 與 商務用 Skype 線上之間的聯合，請參閱這篇文章：設定[Lync Online](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer)客戶的聯合支援。

- 當 Microsoft 365 或 Office 365 中的兩位使用者彼此在個別網域上彼此通訊時，他們只能使用 商務用 Skype 功能 (例如，在兩個組織開啟的視像交談或桌面共用) 。 商務用 Skype

- 如果商務用 Skype使用者被置於 In-Place 或訴訟保留狀態，該使用者與其他 商務用 Skype 或 Skype 使用者之間的任何 IM 交談都會儲存于其信箱中的可復原專案中。  這些交談不會儲存于信箱中的交談記錄資料夾中。

## <a name="turn-off-external-communication-for-specific-individuals"></a>關閉特定人員的外部通訊

<a name="bk_preview"> </a>

啟用整個企業的外部通訊之後，您可以只針對特定人員關閉外部通訊。
  
1. 使用您的帳戶或Microsoft 365 Office 365帳戶進行登錄。

2. 在系統管理中心，前往使用者  >  **活動使用者**。

3. 在使用者清單中，選擇使用者，然後在 [其他 **設定下，** 按一下 [編輯商務用 Skype **屬性**。

    ![選擇 商務用 Skype。](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. 在系統 **管理商務用 Skype，** 選擇 **外部通訊**。

    在選項 **頁面上** ，會選取所有選項。 清除您想要停用的通訊。 下圖顯示 Jakob 將能夠與其他信任企業中的人員通訊，但無法與其他Skype通訊。

    ![選擇外部連絡人。](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. 選擇 **儲存**。

> [!NOTE]
> 您可能必須等候最多 24 小時，變更才能生效。
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>相關主題

<a name="bk_preview"> </a>

[設定商務用 Skype Online](set-up-skype-for-business-online.md)
  
[讓商務用 Skype 使用者新增 Skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)
