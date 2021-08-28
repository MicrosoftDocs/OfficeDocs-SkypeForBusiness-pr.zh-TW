---
title: 設定商務用 Skype Server 以使用 Exchange Server 封存
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 摘要：設定 Exchange Server 2016 或 Exchange Server 2013 及商務用 Skype Server 的 IM 記錄。
ms.openlocfilehash: f264b347660df032b67f06ddf605e99ba97a32b2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603060"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>設定商務用 Skype Server 以使用 Exchange Server 封存

**摘要：** 設定 Exchange Server 2016 或 Exchange Server 2013 及商務用 Skype Server 的 IM 記錄。

商務用 Skype Server 讓管理員可以選擇將立即訊息和 Web 會議記錄封存到使用者的 Exchange Server 2016 或 Exchange Server 2013 信箱，而不是 SQL Server 資料庫。 若您啟用了此選項，系統就會將記錄寫入使用者信箱的「清理」資料夾。 「清理」資料夾是「可復原項目」資料夾中的隱藏資料夾。 雖然使用者看不到此資料夾，但該資料夾是由 Exchange 搜尋引擎進行索引的，可使用 Exchange 信箱搜尋和/或 Microsoft SharePoint Server 2013 來探索。 因為資訊儲存在 Exchange In-Place 保留] 功能所使用的同一個資料夾中 (負責封存電子郵件及其他 Exchange 通訊) ，所以系統管理員可以使用單一工具來搜尋所有為使用者所歸檔的電子通訊。

> [!IMPORTANT]
> 若要完全停用交談封存，您也必須停用交談記錄。 如需詳細資訊，請參閱下列主題：在商務用 Skype Server、 [New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps)和[Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps)[中管理內部與外部通訊](/previous-versions/office/lync-server-2013/lync-server-2013-managing-the-archiving-of-internal-and-external-communications)的封存。

若要將記錄封存至 Exchange Server，必須先設定商務用 Skype Server 和 Exchange Server 之間的伺服器對伺服器驗證。 在進行伺服器對伺服器驗證之後，您可以在商務用 Skype Server 中執行下列工作 (請注意，視您的設定和設定而定，您可能不需要完成下列所有工作) ：

1. 修改您的商務用 Skype Server 封存設定設定，以啟用 Exchange 封存。 所有部署都必須進行此步驟。

2. 針對使用者的內部及/或外部通訊，啟用封存。所有部署都必須進行此步驟。

3. 針對每個使用者設定 ExchangeArchivingPolicy 屬性。 只有在商務用 Skype Server 和 Exchange Server 位於不同樹系時，才需要此步驟。

## <a name="step-1-enabling-exchange-archiving"></a>步驟1：啟用 Exchange 封存

商務用 Skype Server 中的封存主要是使用封存設定設定進行管理。 當您安裝商務用 Skype Server 時，系統會自動為您提供這些設定的單一全域集合。  (管理員可以選擇性地在網站範圍建立新的封存設定集合。 ) 依預設，全域設定中不會啟用封存，也不會在這些設定中啟用 Exchange 封存。 為了使用 Exchange 封存，管理員必須在這些設定設定中設定 EnableArchiving 和 EnableExchangeArchiving 屬性。 EnableArchiving 屬性可設定為下列三個可能值之一：

- **None**。 封存已停用。 這是預設值。 如果 EnableArchiving 設定為 [無]，則不會將任何商務用 Skype Server 封存資料庫或 Exchange Server 中的任何檔案封存。

- **ImOnly**。 只封存立即訊息記錄。 如果已啟用 Exchange 封存，這些記錄會在 Exchange Server 中封存。 如果停用 Exchange 封存，就會將這些記錄封存至商務用 Skype Server。

- **ImAndWebConf**。 立即訊息記錄和 Web 會議記錄皆已封存。 如果已啟用 Exchange 封存，這些記錄會在 Exchange Server 中封存。 如果停用 Exchange 封存，就會將這些記錄封存至商務用 Skype Server。

EnableExchangeArchiving 屬性為 Boolean 值：將 EnableExchangeArchiving 設定為 True ($True) 啟用 Exchange 封存，或將 EnableExchangeArchiving 設定為 False ($False) 以停用 Exchange 封存。 例如，此命令可啟用立即訊息記錄的封存，也可讓 Exchange 封存：

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

若要停用 Exchange 封存，請使用類似下列的命令，它可啟用立即訊息封存，但會停用封存至 Exchange (換句話說，將會將記錄封存到商務用 Skype Server) ：

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> 如果 EnableArchiving 屬性設定為 [無]，則商務用 Skype Server 根本不會封存立即訊息和 Web 會議記錄。 在這種情況下，伺服器會忽略 EnableExchangeArchiving 所設定的值。

您也可以使用商務用 Skype Server (或停用) 來啟用 Exchange 封存。 若要執行這項作業，請完成下列程序：

1. 在控制台中，按一下 [監控和封存]，然後按一下 [封存組態]。

2. 在 [封存組態] 索引標籤中，按兩下要修改的封存設定集合 (例如，[全域] 集合)。

3. 在 [編輯封存設定] 窗格中，按一下 [封存設定] 下拉式清單，然後選取 [封存 IM 工作階段] (若只要封存立即訊息工作階段) 或 [封存 IM 和 Web 會議工作階段] (若要封存立即訊息和 Web 會議工作階段)。

4. 選擇要封存的專案後，請選取 [ **Exchange Server 整合**] 核取方塊，以啟用 Exchange 封存。 若要停用 Exchange 封存，請清除此核取方塊。

> [!NOTE]
> 若 [封存設定] 是設為 [停用封存]，就無法使用 [Exchange 伺服器整合] 核取方塊。 您必須先啟用封存，然後啟用 Exchange 封存。

如果商務用 Skype Server 和 Exchange Server 位於相同樹系中，則針對個別使用者所進行的封存 (或至少針對在 Exchange Server) 上具有電子郵件帳戶的使用者，是使用 Exchange In-Place 保留原則來管理。 如果您有位於舊版 Exchange 的使用者，則會使用商務用 Skype Server 封存原則來管理那些使用者的封存。 請注意，只有在 Exchange Server 2016 或 Exchange Server 2013 上具有帳戶的使用者，才能將其商務用 Skype 記錄封存到 Exchange。

如果商務用 Skype Server 和 Exchange Server 位於不同的樹系中，則會透過為個別使用者帳戶設定 ExchangeArchivingPolicy 屬性來管理個別使用者的封存。 請參閱「步驟 3」以了解詳細資訊。

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>步驟 2：啟用內部及/或外部通訊的封存

在您啟用封存 (和 Exchange 封存後) 您必須修改適當的封存原則，以確保實際封存使用者會話。 請注意，只要啟用封存 (步驟 1) 不會導致商務用 Skype Server 開始封存立即訊息和 Web 會議記錄。 相反地，您必須使用封存原則來啟用內部及（或）外部封存。 當您安裝商務用 Skype Server 時，您也會安裝單一的全域封存原則，其中包含兩個屬性：

- **ArchiveInternal**，若設為 True ($True) 表示會封存內部通訊工作階段 (僅涉及組織中具備 Active Directory 帳戶之使用者的工作階段)。

- **ArchiveExternal**，若設為 True ($True) 表示會封存內部通訊工作階段 (涉及組織中至少有一名具備 Active Directory 帳戶之使用者的工作階段)。

根據預設，這兩個選項值都會設為 False，亦即不論內部或外部通訊工作階段都不會受到封存。 若要修改全域原則，您可以使用商務用 Skype Server 管理命令介面和 Set-CsArchivingPolicy Cmdlet。 此命令可啟用內部和外部通訊工作階段的封存：

```powershell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

您也可以在網站範圍或個別使用者範圍，使用 New-CsArchivingPolicy 來建立新的原則。例如，此命令會建立名為 RedmondArchivingPolicy 的新個別使用者封存原則：

```powershell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

若您要建立個別使用者的原則，您就需要將該原則指派給適當的使用者。例如：

```powershell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

您也可以使用「商務用 Skype Server 控制台」來管理封存原則。 在控制台中，按一下 [監控和封存]，然後按一下 [封存原則]。 若要修改現有的原則，按兩下原則 (例如：全域)，然後在 [編輯封存原則] 窗格中，視需要選取或清除 [封存內部通訊] 和 [封存外部通訊] 核取方塊。 若要建立新的封存原則，請按一下 [ **新增** ]，然後選取 [ **網站原則** ] 或 [ **使用者原則**]。 若您建立新的使用者原則，接著就必須存取適當的使用者帳戶 (從 [使用者] 索引標籤)，然後再將新的原則指派給這些使用者。

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>步驟 3：設定 ExchangeArchivingPolicy 屬性

如果商務用 Skype Server 和 Exchange Server 位於不同的樹系中，則在封存設定設定中只啟用 Exchange 封存，就不足。這不會導致立即訊息和網路會議記錄在 Exchange 中封存。 相反地，您也必須設定每個相關商務用 Skype Server 使用者帳戶上的 ExchangeArchivingPolicy 屬性。 您可將此屬性設為下列四個可能值之一：

1. **未初始化**。 表示封存會根據為使用者 Exchange 信箱設定的 In-Place 保留設定而定;如果使用者的信箱尚未啟用 In-Place 暫止狀態，使用者將會在商務用 Skype Server 中封存他或她的郵件和 Web 會議記錄。

2. **UseLyncArchivingPolicy**。 表示使用者的立即訊息和 Web 會議記錄應該以商務用 Skype Server，而不是 Exchange 中封存。

3. **NoArchiving**。 表示使用者的立即訊息和 Web 會議記錄根本不應該封存。 請注意，此設定會覆寫指派給使用者的任何商務用 Skype Server 封存原則。

4. **ArchivingToExchange**。 指出使用者的立即訊息和 Web 會議記錄應該封存到 Exchange，不論 (或尚未) 指派給使用者信箱的 In-Place 保留設定。

例如，若要設定使用者帳戶，使立即訊息和 Web 會議記錄永遠封存至 Exchange 您可以從商務用 Skype Server 管理命令介面，使用類似下列的命令：

```powershell
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

若您想針對群組使用者 (例如，所有位於特定登錄器集區的使用者) 設定相同的封存原則，可使用類似下列的命令：

```powershell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

請注意，您必須使用商務用 Skype Server 管理命令介面 (和 Windows PowerShell) 才能設定 ExchangeArchivingPolicy 屬性的值。 此屬性不會向商務用 Skype Server 中的系統管理員公開。

若您要檢視已指派特定封存原則之所有使用者的清單，您就可以使用類似下列的命令，即可傳回已將 ExchangeArchivingPolicy 屬性設為 Uninitialized 之所有使用者的 Active Directory 顯示名稱：

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

同樣地，此命令會傳回已將 ExchangeArchivingPolicy 屬性設為 UseLyncArchivingPolicy 之使用者的顯示名稱：

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```