---
title: 控制台更新的使用者搜尋
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/21/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: 您可以使用搜尋查詢的結果，為使用者設定商務用 Skype Server。 您可以依顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別元 (URI) 來搜尋使用者。 您也可以使用 [Lync Server 控制台] 或 [Active Directory 使用者及電腦] 嵌入式管理單元來搜尋使用者。
ms.openlocfilehash: 40a1ced2933abe628c7d1e56d9a1a7f66466769e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388491"
---
# <a name="control-panel---updated-user-search"></a>控制台 - 已更新：使用者搜尋

您可以使用搜尋查詢的結果，為使用者設定商務用 Skype Server。 您可以依顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別元 (URI) 來搜尋使用者。 您也可以使用 [Lync Server 控制台] 或 [Active Directory 使用者及電腦] 嵌入式管理單元來搜尋使用者。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在 [ **使用者搜尋** 控制台] 頁面上執行下列工作：

- [搜尋 Lync Server 2010 使用者](/previous-versions/office/lync-server-2013/lync-server-2013-search-for-lync-server-users)

- [啟用或停用 Lync Server 2010 的使用者](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server)

- [移動使用者](move-user.md)

- [移動所有使用者](move-all-users.md)

- [將原則指派給使用者](/previous-versions/office/lync-server-2013/lync-server-2013-assigning-per-user-policies)

- [在2015商務用 Skype Server 中為使用者啟用企業語音](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [設定使用者的同盟、遠端使用者存取和公用 IM 連線能力](/previous-versions/office/lync-server-2013/lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user)

- [設定使用者的電話語音](/previous-versions/office/lync-server-2013/lync-server-2013-configure-telephony-for-a-user)

如需使用商務用 Skype Server 控制台可執行之不同程式的詳細資訊，請參閱[Manage 商務用 Skype Server 2015](../../manage/manage.md)。

## <a name="ui-reference"></a>UI 參考

下列清單說明「使用者搜尋」頁面上的功能表、命令、欄位及屬性。

### <a name="user-search"></a>使用者搜尋

- **搜索** 根據顯示名稱、名字、姓氏、SAM 帳戶名稱、SIP 位址或使用者帳戶的線路 URI 的第一個部分來搜尋使用者。

- **LDAP 搜尋** 輸入 LDAP 運算式，以搜尋使用者。

- **搜尋使用者** 方塊輸入您想要尋找的使用者資料或 LDAP 運算式。

- **找到** 按一下以顯示符合您在 [ **搜尋使用者** 和] 方塊中輸入之搜尋值的使用者。

- **開啟查詢** 按一下以開啟已儲存的搜尋查詢。

- **儲存查詢** 按一下以儲存搜尋查詢。

- **+ Add filter** 按一下以新增其他搜尋準則。

- **搜尋篩選欄位** 選取您要篩選搜尋結果的欄位，並為查詢選取運算子，然後輸入您要搜尋的字串。

- **顯示的使用者上限** 輸入您想要顯示的搜尋結果數目，或使用向上鍵和向下鍵指定數目。

您可以視情況新增其他說明文字。

### <a name="search-results-menus"></a>搜尋結果功能表

- **啟用使用者** 按一下以開啟 [[使用者：新增 Lync Server 使用者](users-new-lync-server-user.md)] 對話方塊，您可以在其中將新使用者新增至商務用 Skype Server。

    若要新增連絡人，請按向下鍵，然後選取 [啟用使用者] 開啟 [[Users: New Contact Objects](users-new-contact-objects.md)] 對話方塊。

- **編輯** 按一下 [ **編輯** ]，然後按一下 [ **顯示詳細資料** ] 以顯示所選使用者的詳細資料，或按一下 [ **選取所有搜尋結果** ] 以選取顯示在結果表格中的所有使用者。

- **行動** 按一下 [ **動作**]，然後選取您要對搜尋結果中選取之使用者執行的動作。 可供使用的動作如下：

  - **重新啟用 Lync Server** 在暫時停用選取的使用者帳戶之後，啟用該帳戶。

  - **暫時停用 Lync Server** 停用商務用 Skype Server 中的使用者帳戶，直到您重新啟用它，但不移除使用者帳戶。

  - **指派原則** 開啟 [ [使用者：指派原則](users-assign-policies.md) ] 對話方塊，您可以在其中設定指派給使用者的原則。

  - **VIEW PIN 狀態** 開啟 [ [使用者： View PIN 碼狀態](users-view-pin-status.md) ] 對話方塊，其中會顯示所選使用者的 PIN 碼資料。

  - **設定 PIN** 開啟 [ [設定 pin](set-pin.md) ] 對話方塊，您可以在其中設定所選使用者的 PIN 碼。

  - **鎖定 PIN** 鎖定使用者的 PIN 碼。

  - **解除鎖定 PIN** 移除使用者 PIN 碼的鎖定。

  - **從 Lync Server 移除** 從商務用 Skype Server 中移除使用者帳戶。 使用者並未從 Active Directory 中移除。

  - **移除使用者憑證** 移除所有授與使用者的憑證。

  - **將選取的使用者移至集** 區開啟 [ [移動使用者](move-user.md) ] 對話方塊，您可以在其中選取要將選取的使用者移至其中的集區。

  - **將所有使用者移至集** 區開啟 [ [移動使用者](move-user.md) ] 對話方塊，您可以在其中選取要將所有選取的使用者移至其中的集區。