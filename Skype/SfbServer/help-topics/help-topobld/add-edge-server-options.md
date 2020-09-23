---
title: 新增 Edge Server 選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
description: 選取您要為 Edge 集區啟用的每一項功能。 根據預設，Edge 集區支援組織中從防火牆外部登入的遠端使用者，方法是使用虛擬私人網路 (VPN) 。 此外，您還可選擇下列 Edge 集區功能：
ms.openlocfilehash: dfcaafce36d525b676a606db4f164dfdd05f26ba
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216564"
---
# <a name="add-edge-server-options"></a>新增 Edge Server 選項

選取您要為 Edge 集區啟用的每一項功能。 根據預設，Edge 集區支援組織中從防火牆外部登入的遠端使用者，方法是使用虛擬私人網路 (VPN) 。 此外，您還可選擇下列 Edge 集區功能：

- 讓包括 Access Edge Service、Web Conferencing Edge Service 以及 A/V Edge Service 的所有 Edge Service 都使用單一完整網域名稱 (FQDN) 與 IP 位址。 如果您沒有選取使用單一 FQDN 與 IP 位址的選項，則您需要在部署程序中針對這三個 Edge Service 分別指定不同的 FQDN 與 IP 位址。 如需 Edge Service 的詳細資訊，請參閱規劃文件中的＜[Components Required for External User Access](https://technet.microsoft.com/library/2d0f9817-14e7-4109-95dc-62420e3c29e2.aspx)＞。

    > [!NOTE]
    > 如果您選取了這個選項，則您必須針對每個 Edge Service 指定不同的連接埠號碼 (建議的預設連接埠設定為：444 適用於 Access Edge Service，8057 適用於 Web Conferencing Edge Service，443 適用於 A/V Edge Service)。選取這個選項之後，您可以接著為這三個服務一併輸入共用的 FQDN，因此有助於防止發生潛在的連線問題，並簡化相關組態設定。

- 支援同盟關係。 如果您想要支援內部使用者與組織外部之信任網域的使用者 (包括支援的公用立即訊息 (IM) 提供者之任何使用者) 進行通訊，請選取這個選項。 如果您選取了這個選項，便需要為特定的同盟網域以及您要支援的公用 IM 連線服務提供者設定支援項目。 如需針對同盟與其他外部使用者存取類型設定支援項目的詳細資訊，請參閱 Edge Server 部署文件中的＜[Configuring Support for External User Access](https://technet.microsoft.com/library/f8424f8c-f965-4414-8485-30f07e10214a.aspx)＞。

    > [!NOTE]
    > 組織裡只有一個前端集區或 Standard Edge Server 可以針對同盟需求對外發行。所有同盟使用者的存取行為，包括公用 IM 使用者，都需經過同一個 Edge 集區或單一 Edge Server。例如，如果您的部署範圍包括分別部署在紐約與倫敦的一個 Edge 集區或單一 Edge Server，而您針對紐約的 Edge 集區或單一 Edge Server 啟用了同盟支援，則同盟使用者的訊號流量會通過紐約的 Edge 集區或單一 Edge Server。儘管位於倫敦的內部使用者在致電倫敦的同盟使用者時，使用了倫敦集區或 Edge Server 以傳送音訊/視訊流量，與倫敦的使用者進行通訊時也適用這種情況。

- 啟用 XMPP 同盟。如果您想支援內部使用者與信任之 XMPP 合作夥伴間的通訊，請選取這個選項。

您可以在部署初始拓撲時新增外部使用者存取的支援，也可以稍後再新增。 如需新增 Edge Server 至現有拓撲的詳細資訊，請參閱 Edge Server 部署文件中的＜[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)＞。


