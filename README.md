# VS Code Next.js snippets

This extension for Visual Studio Code adds snippets for Next.js

## Supported languages (file extensions)

- JavaScript (.js)
- JavaScript React (.jsx)
- TypeScript (.ts)
- TypeScript React (.tsx)

## Basic

|  Prefix | Method                              |
| ------: | ----------------------------------- |
| `impn→` | `import { moduleName } from 'next'` |

## JavaScript/JavaScript React:

### `sp`

```javascript
export const getStaticProps = async (context) => {
  return {
    props: {},
  }
}
```

### `spth`

```javascript
export const getStaticPaths = async () => {
  return {
    paths: [{ params: {} }],
    fallback: true,
  }
}
```

### `ssp`

```javascript
export const getServerSideProps = async (context) => {
  return {
    props: {},
  }
}
```

### `initp`

```javascript
FileName.getInitialProps = async (context) => {
  return {
    props: {},
  }
}
```

### `np`

Creates next page

```javascript
const FileName = () => {
  return <div></div>
}

export default FileName
```

### `npsp`

Creates next page with getStaticProps() method

```javascript
const FileName = () => {
  return <div></div>
}

export const getStaticProps = async (context) => {
  return {
    props: {},
  }
}

export default FileName
```

### `npssp`

Creates next page with getServerSideProps() method

```javascript
const FileName = () => {
  return <div></div>
}

export const getServerSideProps = async (context) => {
  return {
    props: {},
  }
}

export default FileName
```

### `npinitp`

Creates next page with getInitialProps method

```javascript
const FileName = () => {
  return <div></div>
}

FileName.getInitialProps = async (context) => {
  return {}
}

export default FileName
```

### `capp`

Creates custom app function in \_app file

```javascript
const MyApp = ({ Component, pageProps }) => {
  return <Component {...pageProps} />
}

export default MyApp
```

### `cappip`

Creates custom app function with getInitialProps in \_app file

```javascript
const MyApp = ({ Component, pageProps }) => {
  return <Component {...pageProps} />
}

MyApp.getInitialProps = async (appContext) => {
  const appProps = await App.getInitialProps(appContext)

  return { ...appProps }
}

export default MyApp
```

### `cdoc`

Creates custom doc class with getInitialProps in \_document file

```javascript
import Document from 'next/document'

class MyDocument extends Document {
    static async getInitialProps(ctx) {
        const initialProps = await Document.getInitialProps(ctx)

        return initialProps
    }

export default MyDocument
```

### `cdocdom`

Creates custom doc class with getInitialProps and dom tree in \_document file

```javascript
import Document, { Html, Head, Main, NextScript } from 'next/document'

class MyDocument extends Document {
  static async getInitialProps(ctx) {
    const initialProps = await Document.getInitialProps(ctx)
    return { ...initialProps }
  }

  render() {
    return (
      <Html>
        <Head />
        <body>
          <Main />
          <NextScript />
        </body>
      </Html>
    )
  }
}

export default MyDocument
```

## TypeScript/TypeScript React:

### `tssp`

```typescript
export const getStaticProps: GetStaticProps = async (context) => {
  return {
    props: {},
  }
}
```

### `tsspth`

```typescript
export const getStaticPaths: GetStaticPaths = async () => {
  return {
    paths: [{ params: {} }],
    fallback: true,
  }
}
```

### `tsssp`

```typescript
export const getServerSideProps: GetServerSideProps = async (context) => {
  return {
    props: {},
  }
}
```

### `tsnp`

```typescript
import { NextPage } from 'next'

interface Props {}

const FileName: NextPage<Props> = () => {
  return <div></div>
}

export default FileName
```

### `tsnpsp`

```typescript
import { GetStaticProps, NextPage } from 'next'

interface Props {}

const FileName: NextPage<Props> = () => {
  return <div></div>
}

export const getStaticProps: GetStaticProps = async (context) => {
  return {
    props: {},
  }
}

export default FileName
```

### `tsnpssp`

```typescript
import { NextPage, GetServerSideProps } from 'next'

interface Props {}

const FileName: NextPage<Props> = () => {
  return <div></div>
}

export const getServerSideProps: GetServerSideProps = (context) => {
  return {
    props: {},
  }
}

export default FileName
```

### `tsnpinitp`

```typescript
import { NextPage } from 'next'

interface Props {}

const FileName: NextPage<Props> = () => {
  return <div></div>
}

FileName.getInitialProps = async (context) => {
  return {}
}

export default FileName
```

### `tscapp`

```typescript
import { AppProps } from 'next/app'

const MyApp = ({ Component, pageProps }: AppProps) => {
  return <Component {...pageProps} />
}

export default MyApp
```

### `tscdoc`

```typescript
import Document, { DocumentContext } from 'next/document'

class MyDocument extends Document {
    static async getInitialProps(ctx: DocumentContext) {
        const initialProps = await Document.getInitialProps(ctx)

        return initialProps
    }

export default MyDocument
```
