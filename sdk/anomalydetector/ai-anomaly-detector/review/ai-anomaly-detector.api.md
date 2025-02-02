## API Report File for "@azure/ai-anomaly-detector"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

/// <reference types="node" />

import * as coreHttp from '@azure/core-http';
import { KeyCredential } from '@azure/core-auth';
import { PagedAsyncIterableIterator } from '@azure/core-paging';
import { PipelineOptions } from '@azure/core-http';
import { TokenCredential } from '@azure/core-auth';

// @public
export type AlignMode = "Inner" | "Outer";

// @public (undocumented)
export interface AlignPolicy {
    alignMode?: AlignMode;
    fillNAMethod?: FillNAMethod;
    paddingValue?: number;
}

// @public (undocumented)
export class AnomalyDetector extends AnomalyDetectorContext {
    constructor(endpoint: string, options?: AnomalyDetectorOptionalParams);
    deleteMultivariateModel(modelId: string, options?: AnomalyDetectorDeleteMultivariateModelOptionalParams): Promise<coreHttp.RestResponse>;
    detectAnomaly(modelId: string, body: DetectionRequest, options?: AnomalyDetectorDetectAnomalyOptionalParams): Promise<AnomalyDetectorDetectAnomalyResponse>;
    detectChangePoint(body: DetectChangePointRequest, options?: AnomalyDetectorDetectChangePointOptionalParams): Promise<AnomalyDetectorDetectChangePointResponse>;
    detectEntireSeries(body: DetectRequest, options?: AnomalyDetectorDetectEntireSeriesOptionalParams): Promise<AnomalyDetectorDetectEntireSeriesResponse>;
    detectLastPoint(body: DetectRequest, options?: AnomalyDetectorDetectLastPointOptionalParams): Promise<AnomalyDetectorDetectLastPointResponse>;
    exportModel(modelId: string, options?: AnomalyDetectorExportModelOptionalParams): Promise<AnomalyDetectorExportModelResponse>;
    getDetectionResult(resultId: string, options?: AnomalyDetectorGetDetectionResultOptionalParams): Promise<AnomalyDetectorGetDetectionResultResponse>;
    getMultivariateModel(modelId: string, options?: AnomalyDetectorGetMultivariateModelOptionalParams): Promise<AnomalyDetectorGetMultivariateModelResponse>;
    lastDetectAnomaly(modelId: string, body: LastDetectionRequest, options?: AnomalyDetectorLastDetectAnomalyOptionalParams): Promise<AnomalyDetectorLastDetectAnomalyResponse>;
    listMultivariateModel(options?: AnomalyDetectorListMultivariateModelOptionalParams): PagedAsyncIterableIterator<AnomalyDetectorClientModelSnapshot>;
    trainMultivariateModel(body: AnomalyDetectorClientModelInfo, options?: AnomalyDetectorTrainMultivariateModelOptionalParams): Promise<AnomalyDetectorTrainMultivariateModelResponse>;
}

// @public
export class AnomalyDetectorClient extends AnomalyDetector {
    constructor(endpointUrl: string, credential: TokenCredential | KeyCredential, options?: PipelineOptions);
}

// @public (undocumented)
export interface AnomalyDetectorClientErrorResponse {
    code: string;
    message: string;
}

// @public
export interface AnomalyDetectorClientModel {
    createdTime: Date;
    lastUpdatedTime: Date;
    modelId: string;
    modelInfo?: AnomalyDetectorClientModelInfo;
}

// @public
export interface AnomalyDetectorClientModelInfo {
    // (undocumented)
    alignPolicy?: AlignPolicy;
    readonly diagnosticsInfo?: DiagnosticsInfo;
    displayName?: string;
    endTime: Date;
    readonly errors?: AnomalyDetectorClientErrorResponse[];
    slidingWindow?: number;
    source: string;
    startTime: Date;
    readonly status?: AnomalyDetectorClientModelStatus;
}

// @public
export interface AnomalyDetectorClientModelList {
    currentCount: number;
    maxCount: number;
    models: AnomalyDetectorClientModelSnapshot[];
    nextLink?: string;
}

// @public (undocumented)
export interface AnomalyDetectorClientModelSnapshot {
    createdTime: Date;
    // (undocumented)
    displayName?: string;
    lastUpdatedTime: Date;
    modelId: string;
    readonly status: AnomalyDetectorClientModelStatus;
    variablesCount: number;
}

// @public (undocumented)
export interface AnomalyDetectorClientModelState {
    epochIds?: number[];
    // (undocumented)
    latenciesInSeconds?: number[];
    // (undocumented)
    trainLosses?: number[];
    // (undocumented)
    validationLosses?: number[];
}

// @public
export type AnomalyDetectorClientModelStatus = "CREATED" | "RUNNING" | "READY" | "FAILED";

// @public
export interface AnomalyDetectorClientOptions extends PipelineOptions {
}

// @public (undocumented)
export interface AnomalyDetectorClientVariableState {
    effectiveCount?: number;
    endTime?: Date;
    filledNARatio?: number;
    startTime?: Date;
    variable?: string;
}

// @public (undocumented)
export class AnomalyDetectorContext extends coreHttp.ServiceClient {
    constructor(endpoint: string, options?: AnomalyDetectorOptionalParams);
    // (undocumented)
    apiVersion: string;
    // (undocumented)
    endpoint: string;
}

// @public
export interface AnomalyDetectorDeleteMultivariateModelExceptionHeaders {
    xMsErrorCode?: string;
}

// @public
export interface AnomalyDetectorDeleteMultivariateModelOptionalParams extends coreHttp.OperationOptions {
}

// @public
export interface AnomalyDetectorDetectAnomalyExceptionHeaders {
    xMsErrorCode?: string;
}

// @public
export interface AnomalyDetectorDetectAnomalyHeaders {
    location?: string;
}

// @public
export interface AnomalyDetectorDetectAnomalyOptionalParams extends coreHttp.OperationOptions {
}

// @public
export type AnomalyDetectorDetectAnomalyResponse = AnomalyDetectorDetectAnomalyHeaders & {
    _response: coreHttp.HttpResponse & {
        parsedHeaders: AnomalyDetectorDetectAnomalyHeaders;
    };
};

// @public
export interface AnomalyDetectorDetectChangePointExceptionHeaders {
    xMsErrorCode?: string;
}

// @public
export interface AnomalyDetectorDetectChangePointOptionalParams extends coreHttp.OperationOptions {
}

// @public
export type AnomalyDetectorDetectChangePointResponse = DetectChangePointResponse & {
    _response: coreHttp.HttpResponse & {
        bodyAsText: string;
        parsedBody: DetectChangePointResponse;
    };
};

// @public
export interface AnomalyDetectorDetectEntireSeriesExceptionHeaders {
    xMsErrorCode?: string;
}

// @public
export interface AnomalyDetectorDetectEntireSeriesOptionalParams extends coreHttp.OperationOptions {
}

// @public
export type AnomalyDetectorDetectEntireSeriesResponse = DetectEntireResponse & {
    _response: coreHttp.HttpResponse & {
        bodyAsText: string;
        parsedBody: DetectEntireResponse;
    };
};

// @public
export interface AnomalyDetectorDetectLastPointExceptionHeaders {
    xMsErrorCode?: string;
}

// @public
export interface AnomalyDetectorDetectLastPointOptionalParams extends coreHttp.OperationOptions {
}

// @public
export type AnomalyDetectorDetectLastPointResponse = DetectLastPointResponse & {
    _response: coreHttp.HttpResponse & {
        bodyAsText: string;
        parsedBody: DetectLastPointResponse;
    };
};

// @public
export interface AnomalyDetectorExportModelExceptionHeaders {
    xMsErrorCode?: string;
}

// @public
export interface AnomalyDetectorExportModelOptionalParams extends coreHttp.OperationOptions {
}

// @public
export type AnomalyDetectorExportModelResponse = {
    blobBody?: Promise<Blob>;
    readableStreamBody?: NodeJS.ReadableStream;
    _response: coreHttp.HttpResponse;
};

// @public
export interface AnomalyDetectorGetDetectionResultExceptionHeaders {
    xMsErrorCode?: string;
}

// @public
export interface AnomalyDetectorGetDetectionResultOptionalParams extends coreHttp.OperationOptions {
}

// @public
export type AnomalyDetectorGetDetectionResultResponse = DetectionResult & {
    _response: coreHttp.HttpResponse & {
        bodyAsText: string;
        parsedBody: DetectionResult;
    };
};

// @public
export interface AnomalyDetectorGetMultivariateModelExceptionHeaders {
    xMsErrorCode?: string;
}

// @public
export interface AnomalyDetectorGetMultivariateModelOptionalParams extends coreHttp.OperationOptions {
}

// @public
export type AnomalyDetectorGetMultivariateModelResponse = AnomalyDetectorClientModel & {
    _response: coreHttp.HttpResponse & {
        bodyAsText: string;
        parsedBody: AnomalyDetectorClientModel;
    };
};

// @public
export interface AnomalyDetectorLastDetectAnomalyExceptionHeaders {
    xMsErrorCode?: string;
}

// @public
export interface AnomalyDetectorLastDetectAnomalyOptionalParams extends coreHttp.OperationOptions {
}

// @public
export type AnomalyDetectorLastDetectAnomalyResponse = LastDetectionResult & {
    _response: coreHttp.HttpResponse & {
        bodyAsText: string;
        parsedBody: LastDetectionResult;
    };
};

// @public
export interface AnomalyDetectorListMultivariateModelExceptionHeaders {
    xMsErrorCode?: string;
}

// @public
export interface AnomalyDetectorListMultivariateModelNextExceptionHeaders {
    xMsErrorCode?: string;
}

// @public
export interface AnomalyDetectorListMultivariateModelNextOptionalParams extends coreHttp.OperationOptions {
    skip?: number;
    top?: number;
}

// @public
export type AnomalyDetectorListMultivariateModelNextResponse = AnomalyDetectorClientModelList & {
    _response: coreHttp.HttpResponse & {
        bodyAsText: string;
        parsedBody: AnomalyDetectorClientModelList;
    };
};

// @public
export interface AnomalyDetectorListMultivariateModelOptionalParams extends coreHttp.OperationOptions {
    skip?: number;
    top?: number;
}

// @public
export type AnomalyDetectorListMultivariateModelResponse = AnomalyDetectorClientModelList & {
    _response: coreHttp.HttpResponse & {
        bodyAsText: string;
        parsedBody: AnomalyDetectorClientModelList;
    };
};

// @public
export interface AnomalyDetectorOptionalParams extends coreHttp.ServiceClientOptions {
    apiVersion?: string;
    endpoint?: string;
}

// @public
export interface AnomalyDetectorTrainMultivariateModelExceptionHeaders {
    xMsErrorCode?: string;
}

// @public
export interface AnomalyDetectorTrainMultivariateModelHeaders {
    location?: string;
}

// @public
export interface AnomalyDetectorTrainMultivariateModelOptionalParams extends coreHttp.OperationOptions {
}

// @public
export type AnomalyDetectorTrainMultivariateModelResponse = AnomalyDetectorTrainMultivariateModelHeaders & {
    _response: coreHttp.HttpResponse & {
        parsedHeaders: AnomalyDetectorTrainMultivariateModelHeaders;
    };
};

// @public (undocumented)
export interface AnomalyInterpretation {
    // (undocumented)
    contributionScore?: number;
    // (undocumented)
    correlationChanges?: CorrelationChanges;
    // (undocumented)
    variable?: string;
}

// @public (undocumented)
export interface AnomalyState {
    errors?: AnomalyDetectorClientErrorResponse[];
    timestamp: Date;
    // (undocumented)
    value?: AnomalyValue;
}

// @public (undocumented)
export interface AnomalyValue {
    // (undocumented)
    interpretation?: AnomalyInterpretation[];
    isAnomaly: boolean;
    score: number;
    severity: number;
}

// @public (undocumented)
export interface CorrelationChanges {
    changedValues?: number[];
    changedVariables?: string[];
}

// @public
export interface DetectChangePointRequest {
    customInterval?: number;
    granularity: TimeGranularity;
    period?: number;
    series: TimeSeriesPoint[];
    stableTrendWindow?: number;
    threshold?: number;
}

// @public
export interface DetectChangePointResponse {
    confidenceScores?: number[];
    isChangePoint?: boolean[];
    readonly period?: number;
}

// @public
export interface DetectEntireResponse {
    expectedValues: number[];
    isAnomaly: boolean[];
    isNegativeAnomaly: boolean[];
    isPositiveAnomaly: boolean[];
    lowerMargins: number[];
    period: number;
    severity?: number[];
    upperMargins: number[];
}

// @public
export interface DetectionRequest {
    endTime: Date;
    source: string;
    startTime: Date;
}

// @public
export interface DetectionResult {
    // (undocumented)
    resultId: string;
    results: AnomalyState[];
    // (undocumented)
    summary: DetectionResultSummary;
}

// @public (undocumented)
export interface DetectionResultSummary {
    errors?: AnomalyDetectorClientErrorResponse[];
    setupInfo: DetectionRequest;
    status: DetectionStatus;
    // (undocumented)
    variableStates?: AnomalyDetectorClientVariableState[];
}

// @public
export type DetectionStatus = "CREATED" | "RUNNING" | "READY" | "FAILED";

// @public
export interface DetectLastPointResponse {
    expectedValue: number;
    isAnomaly: boolean;
    isNegativeAnomaly: boolean;
    isPositiveAnomaly: boolean;
    lowerMargin: number;
    period: number;
    severity?: number;
    suggestedWindow: number;
    upperMargin: number;
}

// @public
export interface DetectRequest {
    customInterval?: number;
    granularity?: TimeGranularity;
    imputeFixedValue?: number;
    imputeMode?: ImputeMode;
    maxAnomalyRatio?: number;
    period?: number;
    sensitivity?: number;
    series: TimeSeriesPoint[];
}

// @public (undocumented)
export interface DiagnosticsInfo {
    // (undocumented)
    modelState?: AnomalyDetectorClientModelState;
    // (undocumented)
    variableStates?: AnomalyDetectorClientVariableState[];
}

// @public
export type FillNAMethod = string;

// @public
export type ImputeMode = string;

// @public
export const enum KnownFillNAMethod {
    // (undocumented)
    Fixed = "Fixed",
    // (undocumented)
    Linear = "Linear",
    // (undocumented)
    NotFill = "NotFill",
    // (undocumented)
    Previous = "Previous",
    // (undocumented)
    Subsequent = "Subsequent",
    // (undocumented)
    Zero = "Zero"
}

// @public
export const enum KnownImputeMode {
    // (undocumented)
    Auto = "auto",
    // (undocumented)
    Fixed = "fixed",
    // (undocumented)
    Linear = "linear",
    // (undocumented)
    NotFill = "notFill",
    // (undocumented)
    Previous = "previous",
    // (undocumented)
    Zero = "zero"
}

// @public (undocumented)
export enum KnownTimeGranularity {
    daily = "daily",
    hourly = "hourly",
    monthly = "monthly",
    none = "none",
    perMicrosecond = "microsecond",
    perMinute = "minutely",
    perSecond = "secondly",
    weekly = "weekly",
    yearly = "yearly"
}

// @public (undocumented)
export interface LastDetectionRequest {
    detectingPoints: number;
    variables: VariableValues[];
}

// @public (undocumented)
export interface LastDetectionResult {
    // (undocumented)
    results?: AnomalyState[];
    // (undocumented)
    variableStates?: AnomalyDetectorClientVariableState[];
}

// @public
export type TimeGranularity = "yearly" | "monthly" | "weekly" | "daily" | "hourly" | "minutely" | "secondly" | "microsecond" | "none";

// @public
export interface TimeSeriesPoint {
    timestamp?: Date;
    value: number;
}

// @public (undocumented)
export interface VariableValues {
    name: string;
    timestamps: string[];
    values: number[];
}

// (No @packageDocumentation comment for this package)

```
