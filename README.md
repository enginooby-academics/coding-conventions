<a name="0"></a>  
# Table of Contents
1. [Abbreviations](#abbreviations)
2. [Naming](#naming) 
    + Variable & constant
    + Type & function
    + Git
3. [Commenting](#commenting)
    + Document
    + Task
    + Section
4. [Architecture](#architecture)
    + SASS/Less
    + NodeJS & TypeScript

<a name="abbreviations"></a>  
### I - Abbreviations
[⬆ To the top](#0)
> Should be **universally accepted**, provide **good result of shortening (>40%)**, used for naming & commenting
* **addr** address - **app** application
* **bg** background - **btn** button
* **char** character - **col** column - **coord** coordinate
* **db** database - **dest** destination - **dir** directory
* **len** length
* **msg** message
* **num** number
* **obj** object
* **pwd** password - **param** parameter - **pic** picture - **pos** position
* **str** string - **src** source
* **val** value - **var** variable - **vec** vector

<a name="naming"></a>  
# II - Naming
[⬆ To the top](#0)
> Normally use camelCase for variables & functions/methods, SNAKE_CASE for constants, PascalCase for types, w/ prefix if necessary

### 1 - Variable & Constant
+ **Exceptions** (Go - exported) ```PascalCase```
+ **Element/HTMLElement** ```e prefix```: *eBtn*
+ **NodeListOf\<Element>** ```es prefix```: *esBtn*
+ **JQuery\<HTMLElement>** ```$ prefix```: *$btn*
+ **Boolean** ```{is/have/can/do}+{noun}+{adj/verb-ed}```: *wasBtnClicked*, *areBtnsGreen*
+ **Private class member** ```_ prefix```: *_id*
+ **Constant** 
    - (primitive type && project/file/class-scoped) ```SNAKE_CASE | All caps```: *BTN_SELECTOR*
    - (reference type || function-scoped) ```camelCase```
+ **Unit** (interval, dimension) ```in+{unit} suffix```: *delayInSeconds, BTN_WIDTH_IN_METERS*

### 2 - Type & Function
+ **Function** ```camelCase```: *disableBtn()*
    - (async) ```camelCase | Async suffix``` *fetchUsersAsync()*
    - (C#|Unity; C++|Unreal Engine, Go - exported) ```PascalCase```: *DisableBtn()*
+ **Class/struct/record** ```PascalCase```: *CoolBtn*
+ **Interface** ```PascalCase | I prefix```: *IClickable*
+ **Trait** (PHP) ```PascalCase | T prefix```: *TDisplay*
+ **Enum** ```PascalCase | Singular```: *BtnState {Clicked, Focus, Hover, Active, Disabled}*
+ **Event** 
    - (of current class) ```camelCase | on+{ordinal}+{action}```: *onClick()*, *on1stClick()*
    - (of other object) ```camelCase | on+{noun}+{ordinal}+{action}```: *onBtnClick*, *onBtn1stClick*
+ **CSS class** ```BEM```: *hero__btn--round* [[Reference](https://sparkbox.com/foundry/bem_by_example)]

### 3 - Git
+ **Repo name** ```kebab-case | All lower``` (avoid lowerscore _ which seems bad for URL)  
#### Commit message
+ **Initial commit** first commit of the project involving common/familiar setup.
+ **[Exp]** experimenting, trying out a feature. This code can be used for reference later and removed when getting familiar (marked with // REMOVE).
+ **[Refactor]** refactoring code, removing unnecesary code/comments, reorganinzing code/files, etc.
+ **[Fix]**
+ **[Test]**
+ **[Doc]**

<a name="commenting"></a>  
# III - Commenting
[⬆ To the top](#0)
### 1 - Document
+ **Variable & functions**: above, combine with _**docstring**_ if public
```cs
/// <summary>
/// This meta tag has been deprecated in M63
/// </summary>
public string cookie;
```

+ **Output**

Result of single statement: same line
```ts
console.log('foobar') // expected output: foobar
```
Result of block of statements: below
```ts
const a = 'foo'
const b = 'bar'
console.log(a + b)
// expected output: foobar
```
+ **Ordered procedure**: above each line w/ cardinal numbers	
```ts
// 1. Create an interface representing a document in MongoDB
inteface User { name: string...
// 2. Create a Schema corresponding to the document interface
const schema = new Schema<User>({...
// 3...
```
+ **Mixed procedure**: above the procedure + mark according line w/ cardinal numbers	

```css
/**
 * Main content containers
 * 1. Make the container full-width with a maximum width
 * 2. Center it in the viewport
 * 3. Leave some space on the edges, especially valuable on small screens
 */
.container {
  max-width: $max-width; /* 1 */
  margin-left: auto; /* 2 */
  margin-right: auto; /* 2 */
  padding-left: 20px; /* 3 */
  padding-right: 20px; /* 3 */
  width: 100%; /* 1 */
}
```
  
### 2 - Task
+ **TODO** general tasks
+ **FIX**
+ **REMOVE** the code is used for reference later and removed when becoming unneccesary.
+ **ADHOC** temporary code needed to be replaced by more elegant solutions.
+ **REFACTOR** general refactoring tasks
    - **DRY** extract common code block as a function
    - **PARAMETERIZE** replace magic literals by variables
    - **UTIL** utility/helper method should be moved into a dedicated file.
+ **SPECIFIC** the code inside a general framework/library to solve problems for only a specific project, should be moved into that very project
  
### 3 - Section
> Use **upper case** to search by matched case in files (esp. CSS files) containing many categorizes, components, etc. 
+ **Categorize** containing multiple components
```css
/*-------------------------
      BASIC COMPONENTS
-------------------------*/
```

```css
///////////////////////////
//    BASIC COMPONENTS
```
+ **Component**
```css
/* BUTTON */
```

<a name="architecture"></a>  
# IV - Architecture
[⬆ To the top](#0)
> Standard approaches to structure & organize code files
+ **SASS** ```7-1 pattern``` ([reference](https://www.learnhowtoprogram.com/user-interfaces/building-layouts-preprocessors/7-1-sass-architecture))
+ **TS & NodeJS** ([reference](https://github.com/microsoft/TypeScript-Node-Starter))
