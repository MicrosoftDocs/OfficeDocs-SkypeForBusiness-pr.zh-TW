---
title: 控制台更新的使用者搜尋
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/21/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: 您可以使用搜尋查詢的結果來設定商務用 Skype Server 的使用者。 您可以依顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）來搜尋使用者。 您也可以使用 Lync Server [控制台] 或 [Active Directory 使用者和電腦] 管理單元來搜尋使用者。
ms.openlocfilehash: 4d0fc01a5843408effa69aceb5c95a74c875213a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822936"
---
# <a name="control-panel---updated-user-search"></a>使用者搜尋

您可以使用搜尋查詢的結果來設定商務用 Skype Server 的使用者。 您可以依顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）來搜尋使用者。 您也可以使用 Lync Server [控制台] 或 [Active Directory 使用者和電腦] 管理單元來搜尋使用者。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在**使用者搜尋**[控制台] 頁面上執行下列任務：

- [搜尋 Lync Server 2010 使用者](https://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)

- [啟用或停用 Lync Server 2010 的使用者](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)

- [移動使用者](move-user.md)

- [移動所有使用者](move-all-users.md)

- [指派原則給使用者](https://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)

- [在 Lync Server 2013 中為使用者啟用企業語音](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [為使用者設定同盟、遠端使用者存取及公用 IM 連線](https://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)

- [為使用者設定電話語音](https://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)

如需使用商務用 Skype Server [控制台] 所能執行的不同程式的詳細資訊，請參閱[管理商務用 Skype server 2015](../../manage/manage.md)。

## <a name="ui-reference"></a>UI 參考

下列清單說明 [**使用者搜尋**] 頁面上的功能表、命令、欄位及屬性。

### <a name="user-search"></a>使用者搜尋

- **搜尋**依使用者帳戶的顯示名稱、名字、姓氏、SAM 帳戶名稱、SIP 位址或行 URI 的第一個部分來搜尋使用者。

- **LDAP 搜尋**輸入 LDAP 運算式，以搜尋使用者。

- [**搜尋使用者**] 方塊輸入您要搜尋的使用者資料或 LDAP 運算式。

- **尋找**按一下以顯示與您在 [**搜尋使用者**] 和 [方塊] 中輸入之搜尋值相符的使用者。

- **開啟查詢**按一下以開啟已儲存的搜尋查詢。

- [**儲存查詢**]按一下以儲存搜尋查詢。

- **+ 新增篩選**按一下以新增其他搜尋準則。

- **搜尋篩選欄位**選取您要篩選搜尋結果的欄位，選取查詢的運算子，然後輸入您要搜尋的字串。

- **要顯示的使用者數目上限**輸入您想要顯示的搜尋結果數目，或使用向上鍵和向下鍵來指定數位。

視需要新增其他描述性文字。

### <a name="search-results-menus"></a>搜尋結果功能表

- **允許使用者**按一下以開啟 [[使用者：新的 Lync Server 使用者](users-new-lync-server-user.md)] 對話方塊，您可以在其中將新使用者新增至商務用 Skype 伺服器。

    若要新增連絡人，請按一下向下箭號，然後選取 [**啟用連絡人**] 來開啟 [[使用者：新增連絡人物件](users-new-contact-objects.md)] 對話方塊。

- [**編輯**]按一下 [**編輯**]，然後按一下 [**顯示詳細資料**] 以顯示所選使用者的詳細資料，或按一下 [**選取所有搜尋結果**] 以選取 [結果] 表格中顯示的所有使用者。

- **動作**按一下 [**動作**]，然後在搜尋結果中選取您要為選取的使用者執行的動作。 下列動作可供使用：

  - **重新啟用 Lync Server**在已暫時停用所選的使用者帳戶之後，啟用該帳戶。

  - **針對 Lync Server 暫時停**用在商務用 Skype Server 中停用使用者帳戶，直到您重新啟用，而不需移除使用者帳戶。

  - **指派原則**開啟 [[使用者：指派原則](users-assign-policies.md)] 對話方塊，您可以在此設定指派給使用者的原則。

  - **查看 PIN 狀態**開啟 [[使用者：查看 Pin 狀態](users-view-pin-status.md)] 對話方塊，顯示所選使用者的 PIN 資料。

  - **設定 PIN**開啟 [[設定 PIN](set-pin.md) ] 對話方塊，您可以在此設定所選使用者的 PIN。

  - **鎖定 PIN**鎖定使用者的 PIN。

  - **解除鎖定 PIN**移除使用者的 PIN 鎖定。

  - **從 Lync Server 移除**從商務用 Skype Server 移除使用者帳戶。 使用者並未從 Active Directory 中移除。

  - **移除使用者憑證**移除所有授權給使用者的憑證。

  - **將選取的使用者移至 [泳池**]開啟 [[移動使用者](move-user.md)] 對話方塊，您可以在其中選取要將選取的使用者移至其中的 [文件庫]。

  - **將所有使用者移至 [資源庫**]開啟 [[移動使用者](move-user.md)] 對話方塊，您可以在其中選取要將所有選取的使用者移至其中的 [文件庫]。


