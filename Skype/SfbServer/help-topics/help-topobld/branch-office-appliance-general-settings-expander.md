---
title: Branch Office Appliance 一般設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 若要編輯現有 Survivable Branch 裝置或 Survivable Branch 伺服器的設定，您會看到下列區段：
ms.openlocfilehash: 8f77a7b12800d9eba091218de92f4eec17bf2154
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119692"
---
# <a name="branch-office-appliance-general-settings-expander"></a>Branch Office Appliance 一般設定展開工具

若要編輯現有 Survivable Branch 裝置或 Survivable Branch 伺服器的設定，您會看到下列區段：

- 一般設定

- 恢復能力設定

- 中繼伺服器設定



針對 Survivable 分支裝置或 Survivable 分支伺服器，您會看到下列各項：

## <a name="general-settings"></a>一般設定

Survivable Branch 裝置或 Survivable Branch 伺服器的完整功能變數名稱 (FQDN) 。 編輯伺服器的 FQDN 會變更此值。 您必須有符合新值的網域名稱系統 (DNS) 主機 (A) 記錄。

您可以選取 **使用所有設定的 ip 位址** ，或將 **服務使用方式限制為選取的 ip 位址**。 如果您選取 [將 **服務限制為定義的 IP 位址**]，您將會定義伺服器用於所有通訊的主要 IP 位址，但公用交換電話網路 (PSTN) 閘道除外。 您可以為 PSTN 使用定義個別的 IP 位址。

在 [ **關聯**] 中，您可以編輯或指定下列專案：

- 關聯封存伺服器可讓您選取要與 Survivable 分支裝置或 Survivable Branch 伺服器建立關聯的封存伺服器。 您可以從下拉式清單中選取伺服器，以選取已定義的封存伺服器，或按一下 [ **新增** ] 以指定新的封存伺服器。

    > [!IMPORTANT]
    > 在發佈新定義的拓撲之前，您所指定的伺服器必須存在，且必須加入網域。

- [關聯監控伺服器] 可讓您選取要將監控伺服器與 Survivable Branch 裝置或 Survivable Branch 伺服器產生關聯。 您可以從下拉式清單中選取伺服器，以選取已定義的監控伺服器，或按一下 [ **新增** ] 以指定新的監控伺服器。

- 關聯 Edge 集區可讓您選取要將 Edge Server 或集區與 Survivable Branch 裝置或 Survivable Branch 伺服器建立關聯。 您可以從下拉式清單中選取伺服器，以選取已定義的 Edge Server 或集區，或按一下 [ **新增** ] 以指定新的 edge server 或集區。

## <a name="resiliency"></a>彈性

恢復能力提供登錄器集區的高可用性。 透過提供備份註冊機構，如果主要註冊機構失敗，則備份報名者可以接管失敗的註冊機，讓使用者能夠進行登入和通訊。 根據使用主要註冊器失敗的系統，使用者可能會降低功能。

從下拉式清單中，選取 Enterprise Edition 前端集區或 Standard Edition 前端伺服器，該伺服器將充當 Survivable Branch 裝置或 Survivable Branch 伺服器的備份註冊機。 您也可以選取啟用容錯移轉和回退時間間隔。 啟用容錯移轉和回退時間設定 (指定的秒數) 允許自動偵測失敗的註冊機，以及允許自動判斷主要是備份並可接管註冊機構處理常式的回退時間。

> [!IMPORTANT]
> 當定義失敗偵測和回退間隔時，請小心不要輸入當註冊程式在短時間內無法回應時，會發生容錯移轉和回退的間隔。 根據集區或伺服器的載入，主要報名者可能不會在短時間內回應。 Survivable 分支裝置或網站中的 Survivable 分支伺服器的預設值為集區或 Standard Edition 前端伺服器，在容錯移轉和240秒的情況下為120秒的回退。

## <a name="mediation-server"></a>中繼伺服器

針對 **[中繼伺服器]**，您可以指定下列內容：

Survivable Branch 裝置或 Survivable Branch 伺服器上無法使用 [ **組合轉送伺服器已啟用** ] 的核取方塊，因為轉送伺服器是組合。

您可以在集區伺服器上，為傳輸層安全性 (TLS) 定義接聽埠。 此連接埠預設為 5067。 如果您選取 [ **啟用 TCP 埠**]，則必須為組合轉送伺服器定義 TCP 埠。 這是選用的設定，您應該參考閘道或 PSTN 需求，來決定是否需要這項設定。 TCP 連接埠值預設為 5068。

您定義與組合中繼伺服器相關聯的 PSTN 閘道。如果已經定義閘道，它們將可以用來與中繼伺服器相關聯。如果尚未定義任何閘道，但您有可以定義的閘道，則可以選取 **[新增]**。您也可以移除已針對此中繼伺服器設定的閘道。選取閘道，然後按一下 **[移除]**。

如果您有多個閘道與中繼伺服器相關聯，則第一個關聯的閘道將是預設閘道。 如果您必須選擇另一個閘道作為預設閘道，請選取您要設為預設的閘道，然後按一下 [ **成為預設**]。

## <a name="see-also"></a>另請參閱

如需定義及設定 Survivable Branch 裝置或 Survivable Branch Server 之設定的詳細資訊，請參閱 [Branch-Site 恢復性解決方案](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-solutions)。